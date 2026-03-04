# ReactForge - Reaction Trainer

A gamified reaction and lateral movement trainer using webcam-based hand tracking. Think "Dance Dance Revolution for arms."

## How to Play

1. **Serve the file** — any static HTTP server works:
   ```bash
   npx serve .
   ```
   Then open `http://localhost:3000` in **Google Chrome** (recommended for MediaPipe support).

2. **Grant camera access** when prompted.

3. **Press PLAY**, step back so your hands are visible, and **raise both hands** to start the countdown.

4. **Hit targets with the correct hand** — left-hand targets are cyan, right-hand targets are orange. Touch the target with your index fingertip.

5. Targets start in the center zone and progressively unlock mid and far zones as you score hits.

## Scoring

| Component | Points |
|-----------|--------|
| Base hit | 100 |
| Reaction bonus (< 400ms) | up to 150 |
| Movement bonus (distance) | up to 100 |
| Wrong hand penalty | -50 |
| Combo multiplier | x1.0 → x1.5 → x2.0 → x2.5 |

## Settings

- **Difficulty** (Easy / Normal / Hard) — controls spawn delay and miss timeout
- **Total Targets** (10–50)
- **Sound Volume**
- **Hand Cursors** — toggle fingertip dot display
- **CRT Effect** — toggle scanline overlay

Settings and top-10 scores persist in `localStorage`.

## Requirements

- Modern browser with WebRTC (Chrome recommended)
- Webcam
- No install or build step required — single HTML file

## Tech

- [MediaPipe Hands](https://google.github.io/mediapipe/solutions/hands.html) for real-time hand tracking
- Web Audio API for synthesized sound effects
- Single `<canvas>` for mirrored webcam feed, targets, and hand cursors
- Zero dependencies — everything loads from CDN
