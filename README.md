# EX-3 Histogram-of-an-images

## Name : SUJITH A
## Register No : 212224230278

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

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread(r"C:\Users\ADMIN\Downloads\ex.png", cv2.IMREAD_GRAYSCALE)

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

img = cv2.imread(r"C:\Users\ADMIN\Downloads\ex.png", cv2.IMREAD_COLOR)
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
<img width="377" height="434" alt="download" src="https://github.com/user-attachments/assets/54d69fa7-cd95-4010-81c9-90078c0a9fd9" />

### Input Grayscale Image Range

<img width="570" height="434" alt="download" src="https://github.com/user-attachments/assets/257d0f1c-0d1a-4b46-b83c-6734dd4ba90b" />

### Input Grayscale Image Equalized Histogram

<img width="570" height="434" alt="download" src="https://github.com/user-attachments/assets/e88146bf-7f50-4e20-8fa7-6aa0bf8b3371" />

### Histogram of Grayscale Image and Color Image Channels

### Original Image
<img width="377" height="434" alt="download" src="https://github.com/user-attachments/assets/57102671-0eec-49ad-a25c-00045014f0f0" />


### Equalized Image

<img width="377" height="434" alt="download" src="https://github.com/user-attachments/assets/998a88a1-0f95-4f23-823e-3c04831372da" />

### Equalized Histogram
<img width="570" height="434" alt="download" src="https://github.com/user-attachments/assets/fe336cb5-da3c-4f8b-849c-29278be23b6d" />

### Final Output of Original Image and Equalized 

<img width="1206" height="414" alt="download" src="https://github.com/user-attachments/assets/b262b0dd-be03-47a8-8dac-6633bb62bd59" />

### Final Output of Original Image and its Histogram Equalized

<img width="1237" height="372" alt="download" src="https://github.com/user-attachments/assets/341850a0-5da7-4e27-a5c0-3cd390cb072b" />

## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
