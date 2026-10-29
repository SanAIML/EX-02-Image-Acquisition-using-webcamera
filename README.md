# EX-02-Image-Acquisition-using-webcamera
# Aim
To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:
1.Write the frame as a JPG file
2.Display the video
3.Display the video by resizing the window
4.Rotate and display the video
# Software Used
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)

# Algorithm
Step 1: Import the required libraries and initialize the webcam using cv2.VideoCapture().

Step 2: Capture frames continuously from the webcam.

Step 3: Save a frame as a JPG image using cv2.imwrite().

Step 4: Display the live video stream using cv2.imshow().

Step 5: Resize the frame and rotate it using OpenCV functions, then display the processed frames

# Program
```
Developed By:
Name: Sanchita Sandeep
Register No:212224240142

##i) Write the frame as JPG file
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()

captured_image = cv2.imread('captured_frame.jpg')

plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()

##ii) Display the video
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()

##iii) Display the video by resizing the window

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()

##iv) Rotate and display the video
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
# OUTPUT

1) Frame as jpeg
   
<img width="512" height="410" alt="download" src="https://github.com/user-attachments/assets/e4d0ec56-2727-4883-b951-89508079ebaa" />

2) Display the video

<img width="512" height="389" alt="download" src="https://github.com/user-attachments/assets/988dfc7c-d386-4e6e-afb6-f52999a63a06" />

3) Resizing the window

<img width="266" height="389" alt="download" src="https://github.com/user-attachments/assets/62b4c5a7-23b1-4bcc-ab0d-b4cdebbb1bed" />

4) Rotate and Display
<img width="297" height="389" alt="download" src="https://github.com/user-attachments/assets/2e48ab78-b338-487d-b6f9-90e7e8edb7cb" />

# Result
Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.


