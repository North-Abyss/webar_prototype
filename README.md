# WebAR Experience (Modern Glassmorphism)

A premium, browser-based Augmented Reality experience built with **MindAR** and **A-Frame**. This project features a sleek, "Glassmorphism" UI that provides a high-quality user experience without requiring any app installation.

![WebAR Screenshot](https://github.com/North-Abyss/webar_prototype/blob/main/Gemini_Generated_Image-with-QR.png)

## ✨ Features

- **Instant AR**: Runs directly in the browser (Chrome, Safari, Firefox). No app download required.
- **Modern UI**:
    - **Glassmorphism Theme**: Frosted glass effects on menus and instructions.
    - **Sleek Viewfinder**: Minimalist corner guides for a distraction-free experience.
    - **Smart Instructions**: "Point camera at image" prompt that automatically hides when detected.
- **Rich Media**: Supports high-quality video overlays with audio.
- **Audio-First**: Designed to unmute and play video audio automatically upon target detection (subject to browser policies).
- **Responsive**: Adapts gracefully to both mobile and desktop screens.

## 📂 Project Structure

```text
.
├── index.html          # Main Application Entry Protocol
├── css/
│   └── style.css       # Modern Glassmorphism Stylesheet
├── assets/
│   ├── targets.mind    # Compiled MindAR Image Targets
│   └── video.mp4       # content Video Overlay
└── README.md           # Documentation
```

## 🚀 Quick Start

### Prerequisites
You need a simple HTTP server to run this locally because browsers block camera access on `file://` protocols.

### Running Locally

1.  **Clone or Download** this repository.
2.  **Start a Server**:
    If you have Python installed (most Macs/Linux do):
    ```bash
    # Run inside the project directory
    python3 -m http.server
    ```
3.  **Open in Browser**:
    Go to `http://localhost:8000` in your web browser.
4.  **Test**: Allow camera permissions and point your camera at the target image.

### Mobile Testing
To test on your mobile device while running locally, you need to be on the same Wi-Fi network and access your computer's IP address.
*Note: Some browsers block camera on non-secure (http) IP addresses. For best results, use USB port forwarding or deploy to a secure host.*

## 🛠 Customization

### Changing the Target Image
1.  Go to the [MindAR Image Compiler](https://hiukim.github.io/mind-ar-js-doc/tools/compile).
2.  Upload your own target image (JPG/PNG).
3.  Download the compiled `targets.mind` file.
4.  Replace `assets/targets.mind` with your new file.

### Changing the Video
1.  Replace `assets/video.mp4` with your desired video file.
2.  Ensure it is optimized for web (H.264 codec recommended).

## 📱 Troubleshooting

**Camera not opening?**
- Ensure you are using `https://` or `http://localhost`. Browsers block camera access on insecure `http://` domains unless it's localhost.
- Check browser permissions to allow camera access.

**No Audio?**
- The app attempts to unmute automatically, but some mobile browsers require a user interaction first. Tap anywhere on the screen if audio doesn't start immediately.

---

*Built with [MindAR](https://hiukim.github.io/mind-ar-js-doc/) and [A-Frame](https://aframe.io/).*
