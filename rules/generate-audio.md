---
name: generate-audio
description: Generating MP3 voiceover files from text using edge-tts CLI and batch script
---

# Generating Voiceover Audio with edge-tts

## CLI — single file

```bash
edge-tts \
  --voice en-US-AriaNeural \
  --text "Hello, welcome to this video." \
  --write-media public/voiceover/scene-01.mp3 \
  --write-subtitles public/voiceover/scene-01.srt
```

### Options

| Flag | Description | Example |
|------|-------------|---------|
| `--voice` | Voice name | `en-US-AriaNeural` |
| `--rate` | Speech rate | `+10%` or `-10%` |
| `--volume` | Volume | `+0%` |
| `--pitch` | Pitch | `+0Hz` or `-5Hz` |
| `--write-subtitles` | Also output SRT file | |

> For negative values use `=` syntax: `--rate=-20%`

## Batch script — `generate-voiceover.ts`

```ts
import { execSync } from "child_process";
import { mkdirSync } from "fs";

const VOICE = "en-US-AriaNeural";
const RATE = "-5%";
const OUTPUT_DIR = "public/voiceover";

const scenes = [
  { id: "intro",   text: "Welcome to our product overview." },
  { id: "section", text: "Here is how it works." },
  { id: "outro",   text: "Thank you for watching." },
];

mkdirSync(OUTPUT_DIR, { recursive: true });

for (const scene of scenes) {
  const mp3 = `${OUTPUT_DIR}/${scene.id}.mp3`;
  const srt = `${OUTPUT_DIR}/${scene.id}.srt`;
  const text = scene.text.replace(/"/g, '\\"');
  console.log(`Generating ${scene.id}...`);
  execSync(
    `edge-tts --voice "${VOICE}" --rate="${RATE}" --text "${text}" --write-media "${mp3}" --write-subtitles "${srt}"`
  );
  console.log(`  ✓ ${mp3}`);
}

console.log("Done.");
```

Run with:
```bash
npx tsx generate-voiceover.ts
```

## Optional: Python API

```python
import asyncio
import edge_tts

async def generate(text: str, voice: str, output: str):
    communicate = edge_tts.Communicate(text, voice)
    await communicate.save(output)

asyncio.run(generate(
    "Hello from edge-tts.",
    "en-US-AriaNeural",
    "public/voiceover/intro.mp3"
))
```

## Optional: Background music via ffmpeg

Generate a free ambient drone track (no download needed):

```bash
mkdir -p public/music
ffmpeg -y \
  -f lavfi -i "sine=frequency=55:duration=120" \
  -f lavfi -i "sine=frequency=110:duration=120" \
  -f lavfi -i "sine=frequency=220:duration=120" \
  -filter_complex "
    [0]volume=0.18[a];[1]volume=0.12[b];[2]volume=0.06[c];
    [a][b][c]amix=inputs=3:duration=longest[mix];
    [mix]aecho=0.8:0.88:60:0.4[echoed];
    [echoed]afade=t=in:st=0:d=4,afade=t=out:st=113:d=7[out]
  " \
  -map "[out]" -ar 44100 -ac 2 \
  public/music/ambient.mp3
```
