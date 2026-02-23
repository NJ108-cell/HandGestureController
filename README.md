🖐️ AI Virtual Hand Gesture Controller
A real-time Hand Gesture Recognition System built using OpenCV, MediaPipe, and PyAutoGUI that allows you to control your computer using hand gestures.

This project enables:
🖱️ Cursor movement
🔊 Volume control
📜 Scrolling

👆 Left & Right Click
All without touching your mouse or keyboard.

🚀 Project Overview
This system uses your webcam to detect hand landmarks and interpret specific finger combinations as commands.
The program:
Detects hand landmarks using MediaPipe
Identifies finger positions
Maps gestures to system actions
Controls mouse and volume in real time
It is optimized with smoothing techniques to provide stable cursor movement.

🧠 Features
✅ Real-Time Hand Tracking
Uses MediaPipe Hands solution
Tracks up to 1 hand
High detection and tracking confidence

✅ Cursor Control Mode
Move mouse pointer using index finger
Smoothened movement using interpolation
Left click using thumb pinch
Right click using pinky pinch

✅ Volume Control Mode
Adjust system volume using distance between thumb and index finger
Real-time volume bar display
Smooth volume transition

✅ Scroll Mode
Scroll up/down using two-finger vertical gesture
Scroll direction detection
Scroll readiness detection

✅ FPS Display
Real-time performance monitoring
🛠️ Technologies Used
Python 3.x
OpenCV
MediaPipe
NumPy
PyAutoGUI
Pycaw (Windows Volume Control)
Comtypes

📂 Project Structure
📦 Hand Gesture Controller
 ┣ 📜 HandTrackingModule.py
 ┣ 📜 main.py
 ┗ 📜 README.md
 
🔹 HandTrackingModule.py
Contains the HandDetector class:
Detects hands
Extracts landmark positions
Draws hand connections

🔹 main.py
Main controller logic:
Gesture detection
Mode switching
Volume control
Cursor control
Scroll control

✋ Gesture Controls
Gesture	Action
✊ All fingers closed	Neutral mode
☝ Index finger up	Scroll Mode
👍 Thumb + Index up	Volume Mode
✋ All fingers open	Cursor Mode
🤏 Thumb pinch	Left Click
🤏 Pinky pinch	Right Click
⚙️ Installation Guide
1️⃣ Clone the Repository
git clone https://github.com/your-username/hand-gesture-controller.git
cd hand-gesture-controller
2️⃣ Install Dependencies
pip install opencv-python mediapipe numpy pyautogui pycaw comtypes

⚠️ Pycaw works only on Windows for volume control.

▶️ How to Run
python main.py

Press Q to exit the application.

🎯 How It Works
Hand Detection
Converts frame to RGB
Processes using MediaPipe Hands
Extracts 21 landmark points
Gesture Recognition
Detects finger states (open/closed)
Matches specific combinations
Activates corresponding mode
Cursor Mapping
Maps camera coordinates to screen resolution
Applies smoothing factor to reduce jitter
Uses PyAutoGUI for system control
Volume Mapping
Measures thumb-index distance
Interpolates to system volume range
Updates system audio endpoint

📈 Performance Optimization
Adjustable detection confidence
Adjustable tracking confidence
Cursor smoothing factor
FPS monitoring

🖥️ System Requirements
Windows OS (for volume feature)
Webcam
Python 3.7+

Good lighting conditions

🔐 Limitations
Works best with single hand
Volume control only supported on Windows
Requires good lighting
Background clutter may reduce accuracy

📌 Future Improvements
Multi-hand support
Gesture customization
Mac/Linux volume control support
GUI interface
AI-based gesture learning

🤝 Contributing
Contributions are welcome.
Fork the repository and submit a pull request.

👨‍💻 Author
Developed using OpenCV and MediaPipe to demonstrate real-time AI-based human-computer interaction.
