<div align="center">

# 🖐️ AI Virtual Hand Gesture Controller  

### Control your computer with 2D-animated hand gestures — no mouse, no keyboard, just motion.

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-Real--Time%20Vision-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)
![MediaPipe](https://img.shields.io/badge/MediaPipe-Hand%20Tracking-EF5B25?style=for-the-badge)
![PyAutoGUI](https://img.shields.io/badge/System-Control-222222?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Desktop-16a34a?style=for-the-badge)

<br/>

<!-- Snowy / particle background aesthetic -->
<img src="https://images.pexels.com/photos/11467480/pexels-photo-11467480.jpeg?auto=compress&cs=tinysrgb&w=1200" width="100%" alt="snowy abstract background" />

</div>

---

## 🧩 Overview

**AI Virtual Hand Gesture Controller** is a real-time gesture recognition system that lets you control your computer using only your hand in front of a webcam. It uses **OpenCV**, **MediaPipe**, and **PyAutoGUI** to translate natural finger positions into system actions like cursor movement, clicks, scrolling, and volume control.

The goal is to showcase **AI-driven human–computer interaction** with a smooth, responsive, and visually intuitive flow — like a 2D animated control layer on top of your desktop.

---

## 🧠 Core Capabilities

- 🖱️ **Cursor movement** using your index finger.
- 👆 **Left & Right clicks** using pinch gestures.
- 📜 **Smooth scrolling** using vertical two-finger gestures.
- 🔊 **Volume control** using the distance between fingers (Windows, via Pycaw).
- 🎛️ **Mode-specific behavior** for navigation, scrolling, and audio control.
- 📉 **FPS overlay** to monitor real-time performance.

---

## 🛠 Technologies Used

| Component           | Technology          |
|--------------------|---------------------|
| Hand Detection     | MediaPipe Hands     |
| Computer Vision    | OpenCV             |
| System Control     | PyAutoGUI, Pycaw   |
| Math / Arrays      | NumPy              |
| OS Audio (Windows) | Pycaw, comtypes    |
| Language           | Python 3.x         |

---

## 🧱 Project Structure

```bash
Hand-Gesture-Controller/
├── HandTrackingModule.py   # Hand detection & landmark utilities
├── main.py                 # Gesture logic and system control
└── README.md
```

---

## 🧠 Feature Breakdown

### ✅ Real-Time Hand Tracking
- Uses **MediaPipe Hands** to detect 21 key landmarks.  
- Tracks up to **one hand** with configurable detection and tracking confidence.  
- Draws connections for clear visual feedback.

### ✅ Cursor Control Mode
- Move the mouse pointer using the **index finger tip**.  
- Coordinate mapping from camera space → screen space.  
- **Smoothing / interpolation** reduces jitter for a stable 2D cursor animation.  
- **Left click** with thumb–index pinch.  
- **Right click** with thumb–pinky pinch (configurable).

### ✅ Volume Control Mode (Windows)
- Uses **thumb–index distance** as a volume slider.  
- Mapped to system audio range with interpolation.  
- Visual volume bar overlay for feedback.  
- Powered by **Pycaw** and **comtypes**.

### ✅ Scroll Mode
- Two-finger vertical movement = scroll gesture.  
- Scroll direction (up/down) detected from relative finger movement.  
- Scroll “readiness” logic to avoid accidental scrolling.

### ✅ Performance Overlay
- FPS display rendered on the frame.  
- Tunable detection and tracking confidence.  
- Adjustable smoothing factor for motion.

---

## ✋ Gesture Controls

| Gesture                    | Action           |
|---------------------------|------------------|
| ✊ All fingers closed      | Neutral / Idle   |
| ☝ Index finger up         | Scroll Mode      |
| 👍 Thumb + Index up       | Volume Mode      |
| ✋ All fingers open        | Cursor Mode      |
| 🤏 Thumb pinch            | Left Click       |
| 🤏 Pinky pinch            | Right Click      |

> These gestures can be extended or customized in `main.py`.

---

## ⚙️ Installation Guide

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/hand-gesture-controller.git
cd hand-gesture-controller
```

### 2️⃣ Install Dependencies

```bash
pip install opencv-python mediapipe numpy pyautogui pycaw comtypes
```

> ⚠️ **Note:** Pycaw-based volume control works only on **Windows**.

---

## ▶️ How to Run

```bash
python main.py
```

- The app opens a webcam window.  
- Perform gestures in front of the camera.  
- Press **Q** to exit.

---

## 🎯 How It Works (High Level)

1. **Hand Detection**
   - Capture frame → convert to RGB.  
   - Process with **MediaPipe Hands**.  
   - Extract 21 landmark points per detected hand.

2. **Gesture Recognition**
   - Determine which fingers are up/down.  
   - Match patterns to predefined gesture states.  
   - Switch between **Cursor**, **Scroll**, **Volume**, and **Neutral** modes.

3. **Cursor Mapping**
   - Map landmark coordinates from camera resolution to **screen resolution**.  
   - Apply smoothing:  
     \- New position = previous + (current - previous) / smoothing factor.  
   - Use **PyAutoGUI** to move the cursor and trigger clicks.

4. **Volume Mapping (Windows)**
   - Measure thumb–index distance.  
   - Interpolate to system volume range via Pycaw.  
   - Update system master volume in real-time.

---

## 📈 Performance Tuning

- **Detection confidence**: adjust for more stable or more sensitive detection.  
- **Tracking confidence**: tune for robustness vs responsiveness.  
- **Smoothing factor**: higher value = smoother but less snappy cursor.  
- **Frame size / camera resolution**: balance between clarity and FPS.

---

## 🖥 System Requirements

- **OS**: Windows (for full feature set, especially volume control).  
- **Hardware**:  
  - Webcam  
  - Decent CPU for real-time processing  
- **Software**:  
  - Python 3.7+  
  - Good lighting for optimal detection.

---

## 🔐 Limitations

- Works best with **a single hand** visible in the frame.  
- Volume control currently **Windows-only** (Pycaw).  
- Strong backlight or cluttered backgrounds can reduce accuracy.  
- Designed for desktop usage, not mobile.

---

## 📌 Future Improvements

- Multi-hand support and multi-user modes.  
- GUI interface for configuration and gesture visualization.  
- Mac/Linux-compatible audio control.  
- Per-user **gesture customization** and profiles.  
- ML-based gesture learning (train your own gestures).  
- Enhanced overlays with dynamic 2D effects.

---

## 🤝 Contributing

Contributions are welcome.

1. Fork the repo  
2. Create a feature branch  
3. Implement your changes  
4. Add/update relevant documentation  
5. Open a Pull Request

```bash
git checkout -b feature/add-custom-gesture
git commit -m "Add three-finger screenshot gesture"
git push origin feature/add-custom-gesture
```

---

## 👨‍💻 Author

Developed using **OpenCV** and **MediaPipe** to demonstrate real-time **AI-based human–computer interaction** through hand gestures and 2D motion control.

<div align="center">

### Wave your hand. Command your system.

</div>
