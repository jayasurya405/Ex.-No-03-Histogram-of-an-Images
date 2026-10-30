# Histogram-of-an-images

## Aim

To obtain a histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255. Also, write a Python program using OpenCV to perform histogram equalization.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Read the grayscale and color images using the `cv2.imread()` function.

### Step 2
Display the grayscale and color images using the `imshow()` function.

### Step 3
Use the `cv2.calcHist()` function to calculate the frequency of pixel intensities in the grayscale image.

### Step 4
Use the `cv2.calcHist()` function to calculate the histograms of the Blue, Green, and Red channels of the color image.

### Step 5
Plot and display the histograms of the grayscale image and color image.

## Program

**Developed By:** JAYA SURYA R

**Register Number:** 212225230114

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('sv.jpeg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

img = cv2.imread('sv.jpeg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()

plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

## Output

### Input Grayscale Image

<img width="515" height="560" alt="image" src="https://github.com/user-attachments/assets/69d2b2bb-540c-4ec1-ac63-c8638cdca77b" />

### Input Grayscale Image Range
<img width="760" height="542" alt="image" src="https://github.com/user-attachments/assets/3d6efec2-90f7-4a0f-a033-1371e79367c5" />

### Input Grayscale Image Equalized Histogram
<img width="735" height="580" alt="image" src="https://github.com/user-attachments/assets/9275665d-75c8-42bd-bb0f-5e7202dbfbe3" />


### Histogram of Grayscale Image and Color Image Channels

### Original Image

<img width="483" height="540" alt="image" src="https://github.com/user-attachments/assets/d31c562e-6331-4bce-a404-d7ffb63a0023" />

### Equalized Image

<img width="513" height="536" alt="image" src="https://github.com/user-attachments/assets/9e466aa0-f817-419f-bf3b-69f840d41883" />

### Equalized Histogram
<img width="767" height="533" alt="image" src="https://github.com/user-attachments/assets/a0b9fa4d-7c1e-4980-83ba-b56f8e2bf526" />

### Final Output of Original Image and Equalized 
<img width="1378" height="476" alt="image" src="https://github.com/user-attachments/assets/d8f20ac9-3903-4fec-85e6-60e951b863a6" />

### Final Output of Original Image and its Histogram Equalized
<img width="1377" height="473" alt="image" src="https://github.com/user-attachments/assets/2de9721b-22fc-4f8a-8489-3daac8893c46" />


## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
