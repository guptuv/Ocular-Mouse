# Ocular-Mouse
In this a person can control his mouse(all click and scroll) just by the movement of his eyes

For this one need to import mediapipe and pyautogui for i's use and click allow if asked about camera openeing for proper functioning


Eye-Controlled Mouse with OpenCV, MediaPipe, and PyAutoGUI

**Eye-Controlled Mouse with OpenCV, MediaPipe, and PyAutoGUI**

**Introduction**

This Python script lets you control your mouse using your left eye! It uses libraries like OpenCV, MediaPipe, and PyAutoGUI.

**How it Works**

- It tracks where you look with your left eye.
- The mouse cursor moves as you move your eye left or right.
- Blinking clicks the mouse.

You Could Run it on Pycharm it would be very easy then


#Tips

You can adjust the script to:
Change how sensitive it is to eye movements and blinks.
Add more features like dragging and dropping.
Change how the circles around your eyes look.
How the Code Works

Imports libraries.
Sets up camera and facial landmark detection.
Gets your screen size.
Loops to keep the program running:
Captures a frame from the camera.
Flips the frame horizontally (so it matches your view).
Converts the frame's colors for processing.
Detects facial landmarks.
If a face is found:
Gets the landmarks for the left eye.
Shows circles around some eye landmarks (optional).
Moves the mouse cursor based on where you're looking.
Shows circles around other eye landmarks (optional).
Detects a blink and clicks the mouse if it happens.
Shows the processed frame with circles (if enabled).
Waits for a key press to quit (press "q" or any other key).
Things to Keep in Mind

You might need to adjust the settings based on your lighting and how you blink.
You might need to change which landmarks are used for better control.
The script works best if your webcam is positioned well.
Note

This is a basic version and might need improvements to work perfectly in all situations.

For 
**Running the Script**

1. Install required libraries (assuming Python 3 is installed):

   ```bash
   pip install opencv-python mediapipe pyautogui
2.Run the Script:

   ```bash
   python eye_controlled_mouse.py
