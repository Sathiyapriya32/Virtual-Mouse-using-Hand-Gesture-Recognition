# AI Virtual Mouse using Hand Gesture Recognition

This project implements an AI Virtual Mouse system using hand gesture recognition with OpenCV, MediaPipe, and PyAutoGUI. It allows users to control the mouse cursor and simulate mouse clicks and scrolling using hand gestures captured through a webcam.

## Requirements

Before running the project, make sure you have the following dependencies installed:

- **Python 3.x** (Ensure compatibility with the installed libraries)
- **OpenCV** (for computer vision tasks)
- **MediaPipe** (for hand gesture detection)
- **PyAutoGUI** (for controlling the mouse)
- **NumPy** (for array manipulation)

You can install the required libraries using the following commands:

```bash
pip install opencv-python
pip install mediapipe
pip install pyautogui
pip install numpy
pip install cvzone
```
## Project Setup
Clone the repository or download the source code:

You can either clone the repository from GitHub or download the zip file.

## Install dependencies:

Run the following command in the terminal/command prompt to install the required libraries:

```bash
pip install -r requirements.txt
```
## Launch the webcam and start the system:

The system will use your webcam to capture hand gestures and control the mouse.

## Run the AI Virtual Mouse Script:

After setting up the environment, execute the ai_virtual_mouse.py file to start using the AI Virtual Mouse.

```bash
python ai_virtual_mouse.py
```
## How It Works
Hand Detection
The system uses MediaPipe's HandDetector to detect the user's hand and track the key landmarks. The following gestures are recognized to simulate mouse actions:

## Mouse Movement:

Gesture: Index finger extended (fingers[1] = 1) and thumb finger extended (fingers[0] = 1), middle finger curled (fingers[2] = 0).

Action: Move the mouse cursor based on the position of the index finger.

## Left Click:

Gesture: Index, middle, and thumb fingers extended (fingers[1], fingers[2], fingers[0] = 1), with the index and middle finger positioned close to each other.

Action: Left mouse click (triggered only if thumb is not extended and a delay is not active).

## Right Click:

Gesture: Same as Left Click, but with the thumb extended (fingers[4] = 1).

Action: Right mouse click (triggered only if thumb is extended and a delay is not active).

## Mouse Scroll:

Gesture: Index and middle fingers extended (fingers[1] = 1, fingers[2] = 1), thumb not extended (fingers[0] = 0), pinky finger curled or extended.

Action: Scroll up or down based on the positioning of the fingers.

## Double Click:

Gesture: Index finger extended, middle finger curled (fingers[1] = 1, fingers[2] = 0), no other fingers extended.

## Action: Double-click on the current screen position.

## Delays and Threads
To avoid multiple clicks being triggered too quickly, delays are implemented using separate threads for:

Left Click Delay

Right Click Delay

Double Click Delay

These threads ensure that the clicks and actions are only triggered once within a certain period, preventing accidental multiple clicks.

## Code Explanation
Key Variables:
frameR: Frame reduction (for excluding edges in the camera feed).

cam_w, cam_h: Camera width and height.

cap: Video capture object for the webcam.

detector: MediaPipe hand detector object.

## Functions:
l_clk_delay(): Handles the delay after a left click to avoid multiple clicks.

r_clk_delay(): Handles the delay after a right click to avoid multiple clicks.

double_clk_delay(): Handles the delay after a double click to avoid multiple double-clicks.

## Main Loop:
Capture video feed from the webcam.

Detect the hand landmarks using MediaPipe.

Interpret gestures based on the positions of the detected landmarks.

Perform actions (e.g., move the cursor, click, scroll) based on the recognized gestures.

## Threading:
The click delays are managed through separate threads to allow continuous recognition while avoiding repeated clicks.

## 📸 Screenshots
![Screenshot 2025-04-27 at 3 15 01 PM](https://github.com/user-attachments/assets/e44fe9f6-a3f1-4161-80eb-dcf44980ae4a)
![Screenshot 2025-04-27 at 3 15 38 PM](https://github.com/user-attachments/assets/b5683e3d-ed8a-45f9-acd0-5b355bff9526)
![Screenshot 2025-04-27 at 3 16 49 PM](https://github.com/user-attachments/assets/7f7f3d6f-4b76-437e-b3fd-faed8b59f319)



## 🎥 Project Explanation Video
🎥 [Watch the Video](https://www.linkedin.com/posts/sathiyapriya-s-22ucs048_virtualmouse-ai-handgesture-activity-7237483480400445440-nLAy?utm_source=share&utm_medium=member_desktop&rcm=ACoAAEKubiABTjioeFLfoGOrHXFNNCGvYJ6moX8)
