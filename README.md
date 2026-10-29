# DIGITAL_IMAGE_PROCESSING_TECHNIQUES-

- **Name:** NARENDRA KRISHNAN KS
- **Register Number:** 212225S40096
# Image Capture and Video Processing Using OpenCV

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Capture and save a frame as a JPG image.
2. Display the live video stream.
3. Display the video by resizing the window.
4. Rotate and display the video by 90° clockwise.

## Software Requirements

- **Programming Language:** Python 3.7
- **IDE:** Visual Studio Code (VS Code) / Jupyter Notebook
- **Python Distribution:** Anaconda
- **Library:** OpenCV (`cv2`)

## Algorithm

**Step 1:** Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

**Step 2:** Capture frames continuously from the webcam.

**Step 3:** Save a captured frame as a JPG image using `cv2.imwrite()`.

**Step 4:** Display the live video stream using `cv2.imshow()`.

**Step 5:** Resize the frame to 640 × 480 pixels and display the resized video.

**Step 6:** Rotate the video frame by 90° clockwise using OpenCV functions and display the rotated video.

**Step 7:** Release the webcam and close all OpenCV windows after processing.

#### PROCESSING:
### IMPORTING THE LIBRARIES:
## CODE:
~~~
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
~~~
### i) Write the Frame as a JPG Image
## CODE:
~~~
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("rosh pic.jpg", frame)
cap.release()
captured_image = cv2.imread('rosh pic.jpg')
~~~

### ii) Display the Video

## CODE:
~~~
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
~~~
## OUTPUT:
![alt text](image.png)
### iii) Display the Video by Resizing the Window

## CODE:
~~~
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

~~~
## OUTPUT:
![alt text](image-1.png)
## COMPRESSING :
## CODE:
~~~
ap = cv2.VideoCapture(0)

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
~~~
## OUTPUT:
![alt text](image-2.png)
### v)  Display the Video

## CODE:
~~~
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

~~~
## OUTPUT:
![alt text](image-3.png)
## How to Run the Program

1. Install Python and OpenCV in your environment.
2. Open the project folder in Visual Studio Code.
3. Run the Python program using the VS Code terminal.
4. Allow webcam access if prompted.
5. Verify the saved image and observe the video processing windows.

## Result

Thus, an image was successfully captured from the webcam and saved as a JPG file. The live video was displayed, resized to 640 × 480 pixels, and rotated by 90° clockwise using Python and OpenCV.


