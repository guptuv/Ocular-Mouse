# Ocular-Mouse
In this a person can control his mouse(all click and scroll) just by the movement of his eyes

For this one need to import mediapipe and pyautogui for i's use and click allow if asked about camera openeing for proper functioning


Eye-Controlled Mouse with OpenCV, MediaPipe, and PyAutoGUI

Introduction

This Python script implements a basic eye-controlled mouse using computer vision techniques. It leverages the following libraries:

OpenCV (cv2): For real-time video capture and image processing.
MediaPipe (mp): For facial landmark detection and tracking.
PyAutoGUI: To control the mouse cursor and perform clicks.
Functionality

Tracks the user's left eye movement using facial landmark detection.
Moves the mouse cursor proportionally to the left eye's horizontal position on the screen.
Detects blinking by monitoring the vertical distance between specific left eye landmarks.
Performs a click action when a blink is detected.
Instructions

Installation:

Ensure you have Python 3 installed on your system.

Use pip to install the required libraries:

Bash
pip install opencv-python mediapipe pyautogui
Use code with caution.
content_copy
Running the Script:

Open a terminal or command prompt and navigate to the directory containing the script.

Execute the script using Python:

Bash
python eye_controlled_mouse.py
Use code with caution.
content_copy
Calibration (Optional):

This script assumes the user's face is centered in the camera frame. If you prefer a different calibration approach, you might need to modify the landmark selection logic.

Customization:

The script can be further customized to:
Adjust sensitivity for eye movement and blinking detection.
Implement additional control features (e.g., drag and drop).
Modify visual feedback (e.g., different circle colors).
Code Breakdown:

Imports:

Necessary libraries are imported.
Video Capture and Face Mesh Initialization:

A webcam object is created to capture live video.
A MediaPipe FaceMesh instance is configured with refine_landmarks set to True for improved accuracy.
Screen Resolution Retrieval:

The screen width and height are retrieved using pyautogui.size().
Main Loop:

The loop continuously captures frames from the webcam.
The frame is flipped horizontally to match the user's perspective.
The frame is converted from BGR (OpenCV's default color format) to RGB for compatibility with MediaPipe.
Facial landmarks are detected using face_mesh.process().
Facial Landmark Processing:

If face landmarks are detected (landmark_points is not empty):
Access the facial landmark list for the first detected face.
Iterate through specific landmarks in the left eye region (indices 474 to 477).
Circle these landmarks for visualization (optional).
Calculate the on-screen coordinates (screen_x, screen_y) based on the landmark's normalized position (x, y) and the screen resolution.
Move the mouse cursor to these coordinates using pyautogui.moveTo().
Circle two specific left eye landmarks (indices 145 and 159) for visualization (optional).
Calculate the vertical distance between the two landmarks.
If the distance is less than a threshold (indicating a blink), perform a click and a short delay using pyautogui.click() and pyautogui.sleep().
Image Display:

The processed frame with landmarks (if enabled) is displayed in a window named "Eye Controlled Mouse".
Key Handling:

The script waits for a key press with cv2.waitKey(1). Pressing the "q" key (or any other desired key) will terminate the program.
Additional Considerations:

Adjust the blinking threshold value based on individual blinking patterns and lighting conditions.
Experiment with different eye landmark selections for fine-tuning control.
The script requires a calibrated webcam position for optimal performance.
Disclaimer:

This is a basic implementation and may require further refinement for robust performance in real-world scenarios.
