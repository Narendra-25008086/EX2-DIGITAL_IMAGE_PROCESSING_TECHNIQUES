# Image Capture and Video Processing Using OpenCV

---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## 🛠️ Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  

---

## ⚙️ Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using `cv2.imshow()`.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

---

## 💻 Program

### Developed By:
**Name:** ____________________________  

### Register No:
____________________________  

---
##PROGRAM:
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
```

### i) Write the frame as JPG image
Captured image is saved as `MY.jpg`
```
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite(r"C:\Users\naren\OneDrive\Pictures\Camera Roll\MY.jpg", frame)
cap.release()
captured_image = cv2.imread(r"C:\Users\naren\OneDrive\Pictures\Camera Roll\MY.jpg")
import matplotlib.pyplot as plt

plt.imshow(captured_image[:, :, ::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```
##OUTPUT:
<img width="717" height="407" alt="image" src="https://github.com/user-attachments/assets/54665c53-9cb3-4899-8974-b5c5e3cd18ff" />


### ii) Display the video
Live webcam video is displayed
```
import cv2
import matplotlib.pyplot as plt
import time
from IPython.display import clear_output

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        print("Failed to capture frame")
        break

    resized_frame = cv2.resize(frame, (100, 150))
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.title('Live Webcam Frame')
    plt.axis('off')
    plt.show()

    time.sleep(0.05)

cap.release()
```

##OUTPUT:
<img width="377" height="400" alt="image" src="https://github.com/user-attachments/assets/f5375d56-c135-46a7-83ea-90cedb838d7d" />


### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)
```
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

```
##OUTPUT:

<img width="630" height="410" alt="image" src="https://github.com/user-attachments/assets/ea682ea0-eb57-4f1b-b93b-810ac7cf818b" />



### iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)
```
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
##OUTPUT:

<img width="325" height="440" alt="image" src="https://github.com/user-attachments/assets/ad54d7bb-9f8c-4ac7-b379-1d13f9be92fd" />



## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
