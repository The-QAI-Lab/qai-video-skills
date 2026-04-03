---
name: remotion-integration
description: Wiring edge-tts audio into Remotion with dynamic duration, scenes, transitions, and background music
---

# Integrating edge-tts Audio into Remotion

## 1. Entry point — `src/index.ts`

```ts
import { registerRoot } from "remotion";
import { RemotionRoot } from "./Root";
registerRoot(RemotionRoot);
```

## 2. Root with calculateMetadata — `src/Root.tsx`

`calculateMetadata` reads actual audio durations and auto-sizes the composition.

```tsx
import React from "react";
import { Composition, CalculateMetadataFunction, staticFile } from "remotion";
import { getAudioDuration } from "@remotion/media-utils";
import { MyVideo, Props } from "./Composition";

const FPS = 30;
const TRANSITION_FRAMES = 20;
const SCENE_IDS = ["intro", "section", "outro"];

const calculateMetadata: CalculateMetadataFunction<Props> = async () => {
  const durations = await Promise.all(
    SCENE_IDS.map((id) => getAudioDuration(staticFile(`voiceover/${id}.mp3`)))
  );
  const sceneDurations = durations.map((s) => Math.ceil(s * FPS) + FPS);
  const totalFrames =
    sceneDurations.reduce((sum, d) => sum + d, 0) -
    (SCENE_IDS.length - 1) * TRANSITION_FRAMES;

  return { durationInFrames: totalFrames, props: { sceneDurations } };
};

export const RemotionRoot: React.FC = () => (
  <Composition
    id="MyVideo"
    component={MyVideo}
    fps={FPS}
    width={1920}
    height={1080}
    durationInFrames={1}
    defaultProps={{ sceneDurations: new Array(SCENE_IDS.length).fill(150) }}
    calculateMetadata={calculateMetadata}
  />
);
```

## 3. Main composition — `src/Composition.tsx`

Uses `TransitionSeries` with fade transitions between scenes.

```tsx
import React from "react";
import { AbsoluteFill, Audio, interpolate, staticFile, useCurrentFrame, useVideoConfig } from "remotion";
import { TransitionSeries, linearTiming } from "@remotion/transitions";
import { fade } from "@remotion/transitions/fade";

export type Props = { sceneDurations: number[] };

const TRANSITION_FRAMES = 20;

// Ducked background music
const BackgroundMusic: React.FC<{ totalFrames: number }> = ({ totalFrames }) => {
  const frame = useCurrentFrame();
  const { fps } = useVideoConfig();
  const volume = interpolate(
    frame,
    [0, fps * 4, totalFrames - fps * 5, totalFrames],
    [0, 0.18, 0.18, 0],
    { extrapolateLeft: "clamp", extrapolateRight: "clamp" }
  );
  return <Audio src={staticFile("music/ambient.mp3")} volume={volume} loop />;
};

export const MyVideo: React.FC<Props> = ({ sceneDurations }) => {
  const totalFrames =
    sceneDurations.reduce((s, d) => s + d, 0) -
    (sceneDurations.length - 1) * TRANSITION_FRAMES;

  return (
    <AbsoluteFill>
      <BackgroundMusic totalFrames={totalFrames} />
      <TransitionSeries>
        {sceneDurations.map((dur, i) => (
          <React.Fragment key={i}>
            <TransitionSeries.Sequence durationInFrames={dur}>
              {/* Your scene component here */}
              <ScenePlaceholder id={i} durationInFrames={dur} />
            </TransitionSeries.Sequence>
            {i < sceneDurations.length - 1 && (
              <TransitionSeries.Transition
                presentation={fade()}
                timing={linearTiming({ durationInFrames: TRANSITION_FRAMES })}
              />
            )}
          </React.Fragment>
        ))}
      </TransitionSeries>
    </AbsoluteFill>
  );
};
```

## 4. Scene pattern

Each scene follows this pattern — audio plays automatically for the scene's duration:

```tsx
import { AbsoluteFill, Audio, interpolate, staticFile, useCurrentFrame, useVideoConfig } from "remotion";

export const MyScene: React.FC<{ durationInFrames: number }> = ({ durationInFrames }) => {
  const frame = useCurrentFrame();
  const { fps } = useVideoConfig();

  // Fade in/out
  const opacity = interpolate(
    frame,
    [0, fps * 0.5, durationInFrames - fps * 0.5, durationInFrames],
    [0, 1, 1, 0],
    { extrapolateLeft: "clamp", extrapolateRight: "clamp" }
  );

  // Animate text
  const translateY = interpolate(frame, [0, fps * 0.5], [20, 0], {
    extrapolateRight: "clamp",
  });

  return (
    <AbsoluteFill style={{ background: "#050a12", opacity }}>
      <div style={{ transform: `translateY(${translateY}px)`, color: "white", fontSize: 48 }}>
        Your content here
      </div>
      <Audio src={staticFile("voiceover/scene-id.mp3")} />
    </AbsoluteFill>
  );
};
```

## 5. Render

```bash
# Preview in browser
npm run studio

# Render to MP4
npm run render
```

## Key rules (from Remotion best practices)

- All animations MUST use `useCurrentFrame()` — CSS transitions/animations will not render
- `calculateMetadata` runs server-side — use it to set dynamic duration from audio
- Place all assets in `public/` and access via `staticFile("filename")`
- Use `<TransitionSeries>` for scene sequencing with fade/slide/wipe transitions
- Background music: use `volume` callback with `interpolate` to duck under voiceover
