# WebAR Procedural Prototype

A flexible WebAR experience that detects image targets and overlays videos. It is designed to be **procedurally scalable**: you define your content in a list, and the app builds itself.

## 📂 Project Structure

```
.
├── index.html          # Main App (Contains configuration)
├── assets/
│   ├── targets.mind    # Compiled image targets
│   └── video.mp4       # Video asset
└── README.md
```

## ⚙️ How to Configure

All configuration happens in `index.html` inside the `AR_CONTENT` array.

### 1. The Configuration Array
Open `index.html` and look for the script block at the top:

```javascript
const AR_CONTENT = [
  { videoSrc: './assets/video.mp4', height: 0.5625 }, // Index 0 (First image)
  // Add more here...
];
```

### 2. Adding More Targets
To "go on as needed", simply add more objects to the list. The order matches the order of images in your `targets.mind` file.

**Example for 3 targets:**
```javascript
const AR_CONTENT = [
  { videoSrc: './assets/video_A.mp4', height: 0.5625 }, // Matches Image 0
  { videoSrc: './assets/video_B.mp4', height: 1.0 },    // Matches Image 1
  { videoSrc: './assets/video_C.mp4', height: 0.75 },   // Matches Image 2
];
```

### 3. Assets
1.  **targets.mind**: Use the [MindAR Compiler](https://hiukim.github.io/mind-ar-js-doc/tools/compile). Upload all your images at once (in order!) to generate this single file.
2.  **Videos**: Place your video files in `assets/` and reference them in the config.

## 🚀 Deployment (GitHub Pages)

1.  **Push to GitHub**:
    ```bash
    git init
    git add .
    git commit -m "Initial commit"
    git branch -M main
    git remote add origin https://github.com/USER/REPO.git
    git push -u origin main
    ```
2.  **Enable Pages**: Go to Repo Settings > Pages > Source: `main`.
3.  **Test**: Open the provided GitHub Pages URL on your phone.
