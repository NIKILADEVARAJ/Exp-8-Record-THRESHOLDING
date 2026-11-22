# EXP. 8 – THRESHOLDING USING OPENCV

**NAME:** NIKILA D  
**REG NO:** 212224230187

## Aim

To implement different thresholding techniques using OpenCV and Python to segment an image into foreground and background regions.

## Software Requirements

- Python
- Anaconda
- Jupyter Notebook
- OpenCV
- NumPy
- Matplotlib

## Thresholding Techniques

- Global Thresholding
- Adaptive Thresholding
- Otsu's Thresholding

## Algorithm

1. Import the required libraries: OpenCV, NumPy, and Matplotlib.
2. Read the input image using `cv2.imread()`.
3. Convert the input image into grayscale using `cv2.cvtColor()`.
4. Display the original image.
5. Apply Global Thresholding using `cv2.threshold()` with a threshold value of 127.
6. Apply Adaptive Thresholding using the Gaussian method.
7. Apply Otsu's Thresholding to automatically determine the optimal threshold value.
8. Display all the thresholded images separately.
9. Compare the results of different thresholding techniques.

## Implementation

### 1. Import Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

### 2. Read and Convert the Image

```python
image = cv2.imread('Image.png')

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```

### 3. Display Original Image

```python
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis('off')
```

**OUTPUT:**

<img width="531" height="511" alt="image" src="https://github.com/user-attachments/assets/fd35469b-e467-40a1-ac9d-e394a4d0e6c7" />

### 4. Global Thresholding

```python
_, global_thresholded = cv2.threshold(
    gray_image, 127, 255, cv2.THRESH_BINARY
)

plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')
```

**OUTPUT:**

<img width="552" height="512" alt="image" src="https://github.com/user-attachments/assets/d9c67db1-6b61-4dd4-a19d-cd63000a8edd" />

### 5. Adaptive Thresholding

```python
adaptive_thresholded = cv2.adaptiveThreshold(
    gray_image,
    255,
    cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY,
    11,
    2
)

plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')
```

**OUTPUT:**

<img width="590" height="507" alt="image" src="https://github.com/user-attachments/assets/8d5f458f-1d79-4c64-9424-6a571cab3fce" />

### 6. Otsu's Thresholding

```python
_, otsu_thresholded = cv2.threshold(
    gray_image, 0, 255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)

plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')
```

**OUTPUT:**

<img width="386" height="332" alt="image" src="https://github.com/user-attachments/assets/046024c7-1256-419b-95c0-b461873794e2" />

### 7. Display All Outputs

```python
plt.tight_layout()
plt.show()
```

## Result

Thus, Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques were successfully implemented using OpenCV and Python to segment the input image.
