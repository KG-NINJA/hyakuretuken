# Dragon Ball Scouter HUD (TensorFlow.js)

A single-page web experience that emulates a Dragon Ball-style scouter using TensorFlow.js MoveNet Lightning to estimate a single human pose and visualize battle power in real time.

## Features
- Live webcam feed at 640×480 with neon red HUD frame and green targeting overlay.
- MoveNet Lightning detector from `@tensorflow-models/pose-detection` running fully client-side.
- Neon-green skeleton rendering plus animated frame that pulses when a target is locked.
- Battle Power calculation capped at 530,000 using:
  - average pose confidence
  - left/right balance symmetry
  - vertical alignment of the spine (with upper-body fallback)
- Audio/visual feedback:
  - “pip pip” lock-on tones when a subject is detected
  - high-score flashing HUD and beep burst beyond 500,000
  - special move banners: raise arms for “KAMEHAMEHA CHARGE,” extend right arm for “GALICK GUN AIM,” guard pose for “SPIRIT SHIELD”
- Tweet button sharing the current battle power with `#KGNINJA` and linking to `https://kg-ninja.github.io/DGscouter/`.

## Usage
1. Serve or open `index.html` in a modern browser (Chrome/Edge recommended).
2. Allow webcam access when prompted.
3. Strike different poses to trigger lock-on, battle power readouts, and special move animations.
4. Click **SEND TO TWITTER** to post your current reading.

All inference and rendering are done locally; no backend services are required.
