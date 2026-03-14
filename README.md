# WebAR Engineering Project

A marker-based Web Augmented Reality project built with A-Frame and AR.js.

This app uses the standard Hiro marker to render a rotating 3D model (`Fantasy Inn.glb`) directly in a mobile browser without installing a native app.

## Features

- Marker-based AR tracking using Hiro marker
- Web camera access through AR.js
- GLB model preloading with A-Frame assets
- Rotating 3D model for full-angle viewing
- Ambient and directional lighting for realistic depth
- Ground shadow receiver plane for better model anchoring
- Mobile-responsive UI with loading and status overlay

## Project Structure

- `index.html` - Main WebAR scene and UI
- `Fantasy Inn.glb` - 3D model rendered in AR
- `hiro.png` - Marker image for detection

## Tech Stack

- A-Frame `1.2.0`
- AR.js (A-Frame build)

## How to Run Locally

Because browser camera permissions are stricter for local files, it is best to run from a local HTTP server.

### Option 1: VS Code Live Server

1. Open this folder in VS Code.
2. Install the Live Server extension (if needed).
3. Right-click `index.html` and choose "Open with Live Server".
4. Open the URL on your mobile device (same network) or use your desktop browser.

### Option 2: Python HTTP server

From the project folder:

```bash
python -m http.server 5500
```

Then open:

- `http://localhost:5500`

## How to Use

1. Open the app in a camera-enabled browser.
2. Allow camera access when prompted.
3. Show the Hiro marker (`hiro.png`) to the camera.
4. The 3D Fantasy Inn model appears on the marker and rotates slowly.

## Model Configuration

The current model entity uses:

- `gltf-model="#fantasyInnModel"`
- `scale="0.5 0.5 0.5"`
- slow rotation animation on the Y-axis

If the model appears too large or too small, adjust the scale values in `index.html`.

## Lighting and Shadow Setup

The marker scene includes:

- Ambient light for overall visibility
- Directional light with `castShadow: true`
- Receiver plane with `shadow="receive: true"`
- Renderer shadow map enabled

This combination makes the model look more grounded in AR.

## Troubleshooting

- Blank screen:
  - Ensure camera permission is allowed.
  - Serve via HTTP/HTTPS instead of opening the file directly.
  - Try Chrome on Android for best AR.js compatibility.
- Marker not detected:
  - Use a clear printed Hiro marker.
  - Improve lighting conditions.
  - Keep the marker flat and fully visible.
- Model orientation incorrect:
  - Update the model `rotation` in `index.html`.

## Deployment

You can host this project on:

- GitHub Pages
- Netlify
- Vercel

Important: For camera access, deployment should use HTTPS.

## License

This project is for educational/demo use. Add your preferred open-source license before public distribution.
