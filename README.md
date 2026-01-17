
# 🌌 WebAR Experience: "Hollow Knight" Prototype

![Status](https://img.shields.io/badge/Status-Live-success) ![Tech](https://img.shields.io/badge/Tech-MindAR%20%7C%20A--Frame-blueviolet) ![License](https://img.shields.io/badge/License-MIT-lightgrey)

A premium, browser-based Augmented Reality experience. This project brings static images to life by overlaying video content directly onto physical posters using **MindAR** and **A-Frame**. No app download is required—just scan and watch.

[**🔴 LIVE DEMO**](https://north-abyss.github.io/webar_prototype/)

[View Target Image](https://github.com/North-Abyss/webar_prototype/blob/main/demo-image1.png)

---

## ✨ Features
* **Zero-Install AR:** Runs natively in Chrome, Safari, and Firefox.
* **Glassmorphism UI:** sleek, modern interface with frosted glass effects.
* **Precision Tracking:** Video locks onto the image corners instantly.
* **Smart Audio:** Unmutes audio automatically when the target is detected.
* **Mobile Optimized:** Solves common mobile browser blocks (autoplay/inline playback).

---

## 🛠️ How It Works (The Process)

This project uses **Image Tracking** technology. Here is the flow from start to finish:

1.  **The "Target":** We take a normal image (like a poster) and "compile" it into a data file (`.mind`) that the camera can understand.
2.  **The Recognition:** When your camera sees the physical poster, the browser compares it to the compiled data file.
3.  **The Overlay:** Once a match is found (Homography), the code calculates the exact angle and distance of the poster.
4.  **The Render:** It projects an MP4 video file onto that exact space, sticking to the corners even if you move the camera.

---

## 🚀 Quick Start Guide

### 1. Try it Now (User)
1.  Open the [Live Demo Link](https://north-abyss.github.io/webar_prototype/) on your phone.
2.  Point your camera at the **Target Image** (display it on a monitor or print it out).
3.  Tap "Start AR" to unlock the audio.

### 2. Run it Locally (Developer)
You cannot run this by simply double-clicking `index.html`. You need a local server.

**Option A: VS Code (Easiest)**
1.  Install the "Live Server" extension.
2.  Right-click `index.html` > **Open with Live Server**.

**Option B: Python**
```bash
# Open terminal in project folder
python3 -m http.server 8000
# Go to localhost:8000

```

---

## 🎨 Customization (Make It Yours)

Want to use your own image and video?

### Step 1: Compile Your Image

1. Go to the [MindAR Compiler Tool](https://hiukim.github.io/mind-ar-js-doc/tools/compile).
2. Upload your image (JPG/PNG). High contrast works best!
3. Download the `targets.mind` file.
4. Replace the file in `assets/targets.mind`.

### Step 2: Swap the Video

1. Name your video `video.mp4`.
2. Put it in the `assets/` folder.
3. **Important:** If your video shape is different (e.g., square vs landscape), update the `width` and `height` in `index.html`:
```html
<a-video src="#vid" width="1" height="0.55"></a-video>

```



---

## 📂 Project Structure

```text
.
├── index.html          # The logic (HTML + A-Frame)
├── css/
│   └── style.css       # The look (Glassmorphism UI)
├── assets/
│   ├── targets.mind    # The brain (Compiled Image Data)
│   └── video.mp4       # The content (Video Overlay)
└── README.md           # You are here

```

## 📱 Troubleshooting

| Issue | Solution |
| --- | --- |
| **Spinner stuck on "Loading..."** | Make sure you are using `https://` (Github Pages) or `localhost`. Camera is blocked on unsecure HTTP. |
| **Video doesn't play** | Tap the screen once. Mobile browsers block auto-playing video with sound to save data. |
| **Tracking is jittery** | Ensure your target image has good lighting and isn't too blurry. |

---

*Built with ❤️ by Yuvanesh KS using [MindAR](https://github.com/hiukim/mind-ar-js).*



