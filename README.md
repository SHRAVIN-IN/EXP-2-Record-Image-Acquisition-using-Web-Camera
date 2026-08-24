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
```
PYTHON

import cv2
import numpy as np
import matplotlib.pyplot as plt

# =========================================================
# READ IMAGE
# =========================================================

image = cv2.imread("saveetha.jpg")

if image is None:
    print("Error: saveetha.jpg not found")

else:

    # =====================================================
    # 1. ORIGINAL GRAYSCALE IMAGE
    # =====================================================

    gray_image = cv2.cvtColor(
        image,
        cv2.COLOR_BGR2GRAY
    )

    plt.figure(figsize=(6, 5))
    plt.imshow(gray_image, cmap='gray')
    plt.title("Original Grayscale Image")
    plt.axis("off")
    plt.show()


    # =====================================================
    # 2. ORIGINAL GRAYSCALE HISTOGRAM
    # =====================================================

    plt.figure(figsize=(7, 5))
    plt.hist(
        gray_image.ravel(),
        256,
        range=[0, 256]
    )
    plt.title("Original Grayscale Histogram")
    plt.xlabel("Pixel Intensity")
    plt.ylabel("Frequency")
    plt.xlim([0, 256])
    plt.show()


    # =====================================================
    # 3. EQUALIZED GRAYSCALE IMAGE
    # =====================================================

    equalized_image = cv2.equalizeHist(gray_image)

    plt.figure(figsize=(6, 5))
    plt.imshow(
        equalized_image,
        cmap='gray'
    )
    plt.title("Equalized Grayscale Image")
    plt.axis("off")
    plt.show()


    # =====================================================
    # 4. EQUALIZED GRAYSCALE HISTOGRAM
    # =====================================================

    plt.figure(figsize=(7, 5))
    plt.hist(
        equalized_image.ravel(),
        256,
        range=[0, 256]
    )
    plt.title("Equalized Grayscale Histogram")
    plt.xlabel("Pixel Intensity")
    plt.ylabel("Frequency")
    plt.xlim([0, 256])
    plt.show()


    # =====================================================
    # 5. ORIGINAL COLOR IMAGE
    # =====================================================

    plt.figure(figsize=(6, 5))

    plt.imshow(
        cv2.cvtColor(
            image,
            cv2.COLOR_BGR2RGB
        )
    )

    plt.title("Original Color Image")
    plt.axis("off")
    plt.show()


    # =====================================================
    # 6. B, G, R CHANNEL HISTOGRAM
    # =====================================================

    blue, green, red = cv2.split(image)

    plt.figure(figsize=(8, 5))

    plt.hist(
        blue.ravel(),
        256,
        range=[0, 256],
        alpha=0.5,
        label="Blue"
    )

    plt.hist(
        green.ravel(),
        256,
        range=[0, 256],
        alpha=0.5,
        label="Green"
    )

    plt.hist(
        red.ravel(),
        256,
        range=[0, 256],
        alpha=0.5,
        label="Red"
    )

    plt.title("B, G, R Channel Histogram")
    plt.xlabel("Pixel Intensity")
    plt.ylabel("Frequency")
    plt.xlim([0, 256])
    plt.legend()
    plt.show()


    # =====================================================
    # 7. CONVERT BGR TO HSV
    # =====================================================

    image_hsv = cv2.cvtColor(
        image,
        cv2.COLOR_BGR2HSV
    )


    # =====================================================
    # 8. HISTOGRAM EQUALIZATION ON V CHANNEL
    # =====================================================

    image_hsv[:, :, 2] = cv2.equalizeHist(
        image_hsv[:, :, 2]
    )


    # =====================================================
    # 9. CONVERT HSV BACK TO BGR
    # =====================================================

    enhanced_image = cv2.cvtColor(
        image_hsv,
        cv2.COLOR_HSV2BGR
    )


    # =====================================================
    # 10. ENHANCED COLOR IMAGE
    # =====================================================

    plt.figure(figsize=(6, 5))

    plt.imshow(
        cv2.cvtColor(
            enhanced_image,
            cv2.COLOR_BGR2RGB
        )
    )

    plt.title("Enhanced Color Image")
    plt.axis("off")
    plt.show()


    # =====================================================
    # 11. ENHANCED COLOR HISTOGRAM
    # =====================================================

    blue_eq, green_eq, red_eq = cv2.split(
        enhanced_image
    )

    plt.figure(figsize=(8, 5))

    plt.hist(
        blue_eq.ravel(),
        256,
        range=[0, 256],
        alpha=0.5,
        label="Blue"
    )

    plt.hist(
        green_eq.ravel(),
        256,
        range=[0, 256],
        alpha=0.5,
        label="Green"
    )

    plt.hist(
        red_eq.ravel(),
        256,
        range=[0, 256],
        alpha=0.5,
        label="Red"
    )

    plt.title("Enhanced Color Histogram")
    plt.xlabel("Pixel Intensity")
    plt.ylabel("Frequency")
    plt.xlim([0, 256])
    plt.legend()
    plt.show()


```
### Developed By:
**Name:** S.Jana Shravin

### Register No:
212224243003  

---

## Output

<img width="714" height="469" alt="download" src="https://github.com/user-attachments/assets/b54c665d-d553-4041-9907-e43e20f2adbe" />
<img width="456" height="426" alt="download" src="https://github.com/user-attachments/assets/1bc0bac0-8812-4699-ba45-3f5959e42132" />
<img width="714" height="469" alt="download" src="https://github.com/user-attachments/assets/107dfc7a-16fe-44bd-ac1b-9f10d662bc6e" />
<img width="456" height="426" alt="download" src="https://github.com/user-attachments/assets/4674f6a2-2c38-48c6-b5c8-905e277ee871" />
<img width="637" height="469" alt="download" src="https://github.com/user-attachments/assets/ce748977-364f-48c3-8555-8b582e016e13" />
<img width="456" height="426" alt="download" src="https://github.com/user-attachments/assets/01b7e490-230b-4e02-a308-be82a7787948" />
<img width="637" height="469" alt="download" src="https://github.com/user-attachments/assets/8615d7dc-52ac-4349-879c-6cc95a788eaf" />
<img width="456" height="426" alt="download" src="https://github.com/user-attachments/assets/5f62eb51-7b34-40f0-b0fe-e33cff2ef748" />


## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
