# Image Capture and Video Processing Using OpenCV

---

## Aim
### Developed By:
**Name:**JANA SHRAVIN S
### Register No:
212224243003


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
```

import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

ret, frame = cap.read()

if ret:
    cv2.imwrite("captured_frame.jpg", frame)

cap.release()

captured_image = cv2.imread("captured_frame.jpg")

plt.imshow(captured_image[:, :, ::-1])
plt.title("Captured Frame")
plt.axis("off")
plt.show()

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

## Output:



### i) Write the frame as JPG image
Captured image is saved as `captured_image.jpg`

<img width="512" height="410" alt="download" src="https://github.com/user-attachments/assets/1f7f1dbc-f2e3-4e89-997e-5b160bacced9" />


### ii) Display the video
Live webcam video is displayed

<img width="512" height="389" alt="download" src="https://github.com/user-attachments/assets/60f99400-f7f9-4f51-82f6-3617689ea660" />


### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)

<img width="266" height="389" alt="download" src="https://github.com/user-attachments/assets/095f5940-e049-4b40-8027-91a538e0d868" />


### iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)

<img width="297" height="389" alt="download" src="https://github.com/user-attachments/assets/8e955147-7450-4dbd-9d8b-47d9bae20f6b" />

---

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
