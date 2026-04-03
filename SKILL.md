---
name: edge-tts-remotion
description: Generate free AI voiceovers using Microsoft Edge TTS (no API key) and integrate them into Remotion video compositions with dynamic audio-synced scenes.
metadata:
  tags: edge-tts, tts, voiceover, remotion, video, audio, speech, microsoft
---

## When to use

Use this skill when the user wants to:
- Add voiceovers to Remotion videos without a paid TTS API
- Generate speech audio using Microsoft Edge TTS (free, no API key required)
- Sync narration or voiceover audio with Remotion compositions
- Build cinematic videos with AI-generated voice and data visualizations

## Overview

[edge-tts](https://github.com/rany2/edge-tts) is a free Python tool that uses Microsoft Edge's online TTS service. It requires no API key, no Windows, and no Edge browser. It outputs MP3 audio and optionally SRT subtitle files.

## Setup

Load [./rules/setup.md](./rules/setup.md) for installation and prerequisites.

## Generating voiceover audio

Load [./rules/generate-audio.md](./rules/generate-audio.md) for generating MP3 files from text using edge-tts.

## Integrating with Remotion

Load [./rules/remotion-integration.md](./rules/remotion-integration.md) for wiring the generated audio into a Remotion composition with dynamic duration.

## Voice selection

Load [./rules/voices.md](./rules/voices.md) for the full voice list, recommendations, and speech tuning options.
