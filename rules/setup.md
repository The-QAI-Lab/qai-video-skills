---
name: setup
description: Installing edge-tts, Remotion, and all prerequisites
---

# Setup

## 1. Install edge-tts

```bash
pip install edge-tts
# or for CLI-only use:
pipx install edge-tts
```

Verify:
```bash
edge-tts --version
```

## 2. Create a Remotion project

```bash
mkdir my-video && cd my-video
npm init -y
npm install remotion @remotion/cli @remotion/transitions @remotion/media-utils react react-dom typescript @types/react
```

Add scripts to `package.json`:
```json
{
  "scripts": {
    "voiceover": "npx tsx generate-voiceover.ts",
    "charts": "python3 generate-charts.py",
    "studio": "npx remotion studio src/index.ts",
    "render": "npx remotion render src/index.ts MyComposition out/video.mp4"
  }
}
```

`tsconfig.json`:
```json
{
  "compilerOptions": {
    "target": "ES2020",
    "module": "ESNext",
    "moduleResolution": "bundler",
    "jsx": "react",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true
  },
  "include": ["src"]
}
```

## 3. Project structure

```
my-video/
├── public/
│   ├── voiceover/        ← edge-tts MP3 output
│   ├── charts/           ← Python/matplotlib SVG output (optional)
│   └── music/            ← background music (optional)
├── src/
│   ├── index.ts          ← registerRoot
│   ├── Root.tsx          ← Composition + calculateMetadata
│   ├── Composition.tsx   ← main video component
│   └── scenes.tsx        ← individual scene components
├── generate-voiceover.ts ← edge-tts batch script
├── generate-charts.py    ← matplotlib chart generator (optional)
└── package.json
```

## 4. Optional: Python chart generation

```bash
pip install matplotlib numpy
```

## 5. Optional: Background music via ffmpeg

```bash
# Ubuntu/Debian
sudo apt install ffmpeg

# macOS
brew install ffmpeg
```

## No API key required

edge-tts uses Microsoft Edge's online service directly — no account, no cost. Be aware it depends on an external service and may be rate-limited under heavy use.
