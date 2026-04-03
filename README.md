# QAI Video Skills

> An AI agent skill for generating cinematic videos with AI voiceovers using Microsoft Edge TTS (free, no API key) and Remotion. Covers voice generation, audio-synced scene composition, dynamic duration, and chart/data visualization integration.

---

## About

This skill was built at the **Quantum Athletic Intelligence Lab (QAI Lab)** as part of our applied AI toolchain for research communication, product storytelling, and performance science media. At QAI Lab, we believe AI is a force multiplier — a tool that allows researchers, scientists, and practitioners to produce high-quality outputs faster without sacrificing creative control.

The `edge-tts-remotion` skill was developed to solve a real problem: creating professional video content with voiceovers typically requires expensive TTS APIs, video editing software, and significant production time. This skill eliminates those barriers entirely — using Microsoft Edge's free TTS service and Remotion's React-based video framework to produce cinematic, audio-synced videos from code.

---

## Creator

**William McDonald**
Computational Intelligence Scientist — Graduate Student, University of North Carolina
Founder | Lead Scientist, Quantum Athletic Intelligence Lab

---

## What This Skill Does

This skill gives any compatible AI agent the knowledge to:

| Capability | Description |
|-----------|-------------|
| **Free AI Voiceover** | Generate MP3 audio from any text using Microsoft Edge TTS — 323 voices, 70+ languages, no API key |
| **Dynamic Video Duration** | Auto-size Remotion compositions to match actual audio length via `calculateMetadata` |
| **Scene Composition** | Build multi-scene videos with fade/slide/wipe transitions using `TransitionSeries` |
| **Data Visualization** | Generate Python/matplotlib charts as SVGs and embed them in video scenes |
| **Background Music** | Generate ambient music tracks via ffmpeg (no downloads needed) |
| **Dual Export** | Render to MP4 (H.264) at any resolution via Remotion CLI |

---

## Tech Stack

| Tool | Purpose | Cost |
|------|---------|------|
| [edge-tts](https://github.com/rany2/edge-tts) | Text-to-speech (323 voices) | Free |
| [Remotion](https://remotion.dev) | React-based video composition | Free (open source) |
| [ffmpeg](https://ffmpeg.org) | Audio generation & processing | Free |
| [matplotlib](https://matplotlib.org) | Chart/data visualization | Free |
| [pandoc](https://pandoc.org) | Document conversion | Free |

**Total API cost: $0**

---

## Installation

### Via npx skills (recommended)

```bash
npx skills add The-QAI-Lab/qai-video-skills@edge-tts-remotion -g -y
```

### Manual

```bash
git clone https://github.com/The-QAI-Lab/qai-video-skills.git
cp -r qai-video-skills/edge-tts-remotion ~/.agents/skills/
```

---

## Prerequisites

```bash
# edge-tts
pip install edge-tts

# Node.js (v18+) — for Remotion
node --version

# ffmpeg — for audio generation
sudo apt install ffmpeg        # Ubuntu/Debian
brew install ffmpeg            # macOS

# Python chart generation (optional)
pip install matplotlib numpy
```

---

## Quick Start

```bash
# 1. Create project
mkdir my-video && cd my-video
npm init -y
npm install remotion @remotion/cli @remotion/transitions @remotion/media-utils react react-dom typescript @types/react

# 2. Generate voiceovers
npx tsx generate-voiceover.ts

# 3. Preview in browser
npx remotion studio src/index.ts

# 4. Render to MP4
npx remotion render src/index.ts MyComposition out/video.mp4
```

---

## Voice Options

323 voices across 70+ languages and locales. No API key required.

### Top English voices

| Voice | Gender | Style |
|-------|--------|-------|
| `en-US-AriaNeural` | Female | Confident, positive — great for narration |
| `en-US-GuyNeural` | Male | Passionate — great for promos |
| `en-US-AndrewNeural` | Male | Warm, authentic — great for storytelling |
| `en-US-ChristopherNeural` | Male | Authoritative — great for corporate |
| `en-US-JennyNeural` | Female | Friendly, considerate |
| `en-GB-SoniaNeural` | Female | British, professional |
| `en-GB-RyanNeural` | Male | British, professional |
| `af-ZA-AdriNeural` | Female | Friendly, positive — South African |

See [rules/voices.md](rules/voices.md) for the complete list of all 323 voices.

### Speech tuning

```bash
# Slower, lower pitch
edge-tts --voice en-US-GuyNeural --rate=-15% --pitch=-5Hz \
  --text "Your text here." --write-media out.mp3

# Faster, energetic
edge-tts --voice en-US-AriaNeural --rate=+20% \
  --text "Your text here." --write-media out.mp3
```

---

## Workflow

```
1. Write scene scripts
        ↓
2. generate-voiceover.ts  →  public/voiceover/*.mp3
        ↓
3. generate-charts.py     →  public/charts/*.svg   (optional)
        ↓
4. ffmpeg ambient music   →  public/music/ambient.mp3  (optional)
        ↓
5. Remotion calculateMetadata reads audio durations → sets composition length
        ↓
6. npx remotion render    →  out/video.mp4
```

---

## Compatible Agents

This skill works with any agent that reads from `~/.agents/skills/`. Verified compatible with:

| Agent | Notes |
|-------|-------|
| **Kiro CLI** | Full support — primary development environment |
| **Claude Code** | Auto-detected on install |
| **Codex** | Auto-detected on install |
| **OpenClaw** | Auto-detected on install |
| **Cursor Agent** | Auto-detected on install |
| **Gemini CLI** | Auto-detected on install |
| **GitHub Copilot** | Auto-detected on install |

All agents above are part of the [skills.sh](https://skills.sh) ecosystem.

---

## Skill Structure

```
edge-tts-remotion/
├── SKILL.md                      — skill metadata and rule routing
└── rules/
    ├── setup.md                  — project setup, dependencies, folder structure
    ├── generate-audio.md         — edge-tts CLI, batch script, ffmpeg music
    ├── remotion-integration.md   — calculateMetadata, scenes, transitions, audio
    └── voices.md                 — full 323-voice reference table
```

---

## Example Output

The QAI Lab intro video was built entirely with this skill:
- 6 scenes with fade transitions
- Voice: `af-ZA-AdriNeural` at -5% rate
- Animated neural network grid, HUD overlays, data bars
- 3 Python-generated charts (radar, bar, line)
- Ambient drone music via ffmpeg
- Rendered at 1920×1080, 30fps, ~88 seconds

---

## License

MIT License — free to use, modify, and distribute.

---

## QAI Lab

**Quantum Athletic Intelligence Lab** combines AI modeling, biomechanics, and data science to deliver precision-driven performance insights. Our research spans computational athlete intelligence, neuro-performance systems, smart sensor integration, and advanced computer vision for human movement analysis.

[qailab.org](https://www.qailab.org)
