# Hand-Puzzle — Gesture Capture

Hand-Puzzle is a browser-based photo booth controlled by hand gestures. It runs entirely in the browser — no backend, no install, and no extra build steps required.

---

## Description

Hand-Puzzles capture a photo framed by the user's hands, converts it into a 3x3 puzzle with a monochrome photobooth effect, and lets you assemble the puzzle using pinch gestures. Once completed, the puzzle is saved into a downloadable photo strip.

---

## System Requirements

- Browser: Chrome or Edge (recommended), Firefox
- Hardware: Webcam
- Network: Internet required to download the MediaPipe model (~10MB) on first run
- Local server: The app uses ES modules and camera access and should be served over HTTP (e.g., via a simple local server)

---

## Quick Start

1. Clone the repository (replace with your repo URL):

```bash
git clone https://github.com/VaibhavKhushalani/hand-puzzle.git
cd hand-puzzle
```

2. Serve the folder over HTTP. For example, using Python 3:

```bash
python -m http.server 5500
```

3. Open `http://localhost:5500` in your browser and allow camera access.

---

## Project Structure

```
Hand-Puzzle/
├── index.html        # App entry
├── app.js            # Main logic (tracking, puzzle, gallery)
├── css/
│   └── styles.css    # Styles and layout
└── README.md
```

---

## Controls & Gestures

| Gesture             | Action                                  |
| ------------------- | --------------------------------------- |
| Both hands pinching | Freeze capture area and start countdown |
| Pinch on a piece    | Drag that puzzle piece                  |
| Hold a closed fist  | Save completed puzzle or reset board    |

---

## How it works

1. Present both hands to the camera and pinch to define the capture area.
2. Hold the pinch during the countdown — the photo captures automatically.
3. The captured frame is split into a 3x3 puzzle and a photobooth filter is applied.
4. Reassemble pieces using pinch gestures.
5. When the puzzle is complete, make a fist and hold to save the result to the photo strip with a shatter animation.
6. Download the photo strip once you have 3 saved puzzles.

---

## Tech Stack

- MediaPipe Tasks Vision (v0.10.14) — hand landmark detection
- Canvas 2D API — rendering, puzzle pieces, photobooth effect
- JavaScript (ES Modules) — no frontend framework
- CSS custom properties for theming and layout

All external libraries are loaded via CDN; no package install is required.

---

## Troubleshooting

- Camera not starting: Ensure no other application (Teams, Zoom, etc.) is using the camera.
- Model fails to load: Check your network connection. The model downloads from storage.googleapis.com and the runtime from cdn.jsdelivr.net.
- Black screen: Serve the app over HTTP (not via file://) so camera and modules work correctly.
- Pinch not detected: Improve lighting and ensure fingers are visible and close together until the UI indicates detection.

---

## Browser Support

| Browser       | Support                                 |
| ------------- | --------------------------------------- |
| Chrome / Edge | Recommended                             |
| Firefox       | Supported                               |
| Safari        | Limited (may require extra permissions) |
| Mobile        | Limited (desktop recommended)           |

---

## License

MIT. Free to fork, adapt, and use as your own portfolio.

## Author

**Vaibhav Khushalani** — Full Stack Engineer & AI Builder

[GitHub](https://github.com/VaibhavKhushalani) | [LinkedIn](https://www.linkedin.com/in/vaibhav-khushalani-760217136) | [Medium](https://medium.com/@vaibhavkhushalani) | [Instagram](https://www.instagram.com/vaibhav.create) | [YouTube](https://www.youtube.com/@vaibhav.create)
