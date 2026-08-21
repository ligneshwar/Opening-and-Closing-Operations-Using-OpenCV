# Opening and Closing Operations Using OpenCV

## Aim

To write a Python program using OpenCV to perform morphological Opening and Closing operations on an image.

The program performs the following operations:

- Morphological Opening
- Morphological Closing

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Create or load an input image containing foreground objects.

### Step 3:

Display the original image.

### Step 4:

Create a structuring element (kernel) of suitable size.

### Step 5: Opening Operation

- Apply the Opening operation using the structuring element.
- Opening consists of Erosion followed by Dilation.
- Remove small foreground noises while preserving the shape of larger objects.
- Display the opened image.

### Step 6: Closing Operation

- Apply the Closing operation using the structuring element.
- Closing consists of Dilation followed by Erosion.
- Fill small holes and gaps within foreground objects.
- Display the closed image.

### Step 7:
Compare the original, opened, and closed images.

## Program

## Developed By

**Name:** LIGNESHWAR K

**Register No:** 212223230113

## PROGRAM
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = np.zeros((400, 600), dtype=np.uint8)

cv2.rectangle(img, (80, 100), (220, 250), 255, -1)
cv2.rectangle(img, (300, 100), (500, 250), 255, -1)

cv2.circle(img, (50, 50), 3, 255, -1)
cv2.circle(img, (250, 70), 3, 255, -1)
cv2.circle(img, (550, 300), 3, 255, -1)

cv2.circle(img, (150, 170), 8, 0, -1)
cv2.circle(img, (400, 170), 8, 0, -1)

cv2.rectangle(img, (140, 100), (160, 110), 0, -1)
cv2.rectangle(img, (380, 240), (400, 250), 0, -1)

kernel = np.ones((5, 5), np.uint8)

erosion = cv2.erode(img, kernel, iterations=1)
opening = cv2.dilate(erosion, kernel, iterations=1)

dilation = cv2.dilate(img, kernel, iterations=1)
closing = cv2.erode(dilation, kernel, iterations=1)

plt.figure(figsize=(12, 4))

plt.subplot(1, 3, 1)
plt.imshow(img, cmap="gray")
plt.title("Original")
plt.axis("off")

plt.subplot(1, 3, 2)
plt.imshow(opening, cmap="gray")
plt.title("Opening Image")
plt.axis("off")

plt.subplot(1, 3, 3)
plt.imshow(closing, cmap="gray")
plt.title("Closing Image")
plt.axis("off")

plt.tight_layout()
plt.show()
```

### Original Image

<img width="493" height="363" alt="image" src="https://github.com/user-attachments/assets/4c7da4e5-64c8-435c-bb5f-33dd4249db35" />


### Opening Image

<img width="499" height="361" alt="image" src="https://github.com/user-attachments/assets/69578f26-f0fc-4d10-a962-80d1f35aca83" />

### Closing Image

<img width="487" height="361" alt="image" src="https://github.com/user-attachments/assets/3c8ff681-c372-4145-ac8f-86ec4c83e85c" />


## Result

Thus, the morphological operations **Opening** and **Closing** are successfully implemented using OpenCV. 
