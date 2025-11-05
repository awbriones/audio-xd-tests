---
description: Initialize context for the audio-xd-tests workspace
---

# Audio XD Tests - Project Context

You're working in the **audio-xd-tests** repository, a workspace for experiments with sound and audio in experience design.

## Project Structure

```
audio-xd-tests/
├── index.html                    # Main menu/navigation page
├── experiments/
│   └── visualizer/
│       └── index.html           # Circular audio visualizer experiment
└── assets/                      # Shared resources (images, fonts, etc.)
```

## Current Experiments

### 1. Circular Audio Visualizer (`/experiments/visualizer/`)
- **Purpose**: Real-time audio visualization for recording videos for presentations
- **Features**:
  - Drag-and-drop audio file loading (uses File API for temporary browser storage)
  - Three-band FFT analysis (bass, mid, treble)
  - Three layered circular visualizations with wavy distortion based on frequency amplitude
  - Play/pause controls in bottom-right corner
- **Tech Stack**: p5.js, p5.sound library
- **Visual Design**:
  - Near-black background (#0a0a0a)
  - Bass circle: Purple (#a855f7), inner layer
  - Mid circle: Blue (#3b82f6), middle layer
  - Treble circle: Pink (#ec4899), outer layer
  - Max diameter: 667px (scales responsively)

## Tech Stack

- **p5.js**: Canvas rendering and animation
- **p5.sound**: FFT analysis and audio playback
- **Vanilla HTML/CSS/JS**: No build tools, runs directly in browser
- **File API**: Browser-based drag-and-drop audio handling

## Development Workflow

1. **Local Server Required**: Audio experiments need to run on HTTP server (not file://)
   ```bash
   python3 -m http.server 8000
   # Then open http://localhost:8000
   ```

2. **Adding New Experiments**:
   - Create folder in `/experiments/[experiment-name]/`
   - Add experiment card to main `index.html`
   - Keep consistent styling (dark theme, purple/blue/pink accent colors)

3. **Styling Conventions**:
   - Background: Near-black (#0a0a0a - #1a1a1a)
   - Primary accent: Purple (#a855f7)
   - Secondary accent: Blue (#3b82f6)
   - Tertiary accent: Pink (#ec4899)
   - Text: Light gray (#e0e0e0) on dark background

## Common Tasks

- **Tweaking visualizer parameters**: Edit `experiments/visualizer/index.html`
  - Circle radii: `CIRCLE_LAYERS[].baseRadius`
  - Colors: `CIRCLE_LAYERS[].color`
  - Distortion sensitivity: `map()` ranges for displacement
  - Frequency band ranges: `CIRCLE_LAYERS[].range`

- **Adding new experiments**: Create new folder, link from index, maintain visual consistency

- **Testing audio**: Use drag-and-drop with MP3, WAV, or other browser-supported formats

## Goals

This workspace is designed for:
- UI sound implementation experiments
- Audio visualizers for presentation videos
- Immersive audio experiences
- Sound design prototypes

Keep experiments self-contained, easy to record, and visually consistent with the established dark theme and accent colors.
