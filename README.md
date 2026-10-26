# Histogram-of-an-images

**Developed By:** Sridharan B

**Register Number:** 212225230272

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

img = cv2.imread('srii.jpg', cv2.IMREAD_GRAYSCALE)

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

img = cv2.imread('srii.jpg', cv2.IMREAD_COLOR)
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

<Figure size 640x480 with 1 Axes><img width="342" height="434" alt="image" src="https://github.com/user-attachments/assets/a5b29087-f381-4e13-b1b6-e9d2a3d9479d" />


### Input Grayscale Image Range

<Figure size 640x480 with 1 Axes><img width="579" height="434" alt="image" src="https://github.com/user-attachments/assets/31b3307c-c1b9-4b56-a4c8-a48d0dbf1d12" />


### Input Grayscale Image Equalized Histogram

<Figure size 640x480 with 1 Axes><img width="579" height="434" alt="image" src="https://github.com/user-attachments/assets/0085dac0-84f4-4569-b0a8-703a1fc80d86" />



### Histogram of Grayscale Image and Color Image Channels

### Original Image

<Figure size 640x480 with 1 Axes><img width="342" height="434" alt="image" src="https://github.com/user-attachments/assets/d4291eab-2db1-401f-9c08-dff6753828ce" />


### Equalized Image

<Figure size 640x480 with 1 Axes><img width="579" height="434" alt="image" src="https://github.com/user-attachments/assets/723101ec-0515-4add-b462-e0cd23862f9a" />


### Equalized Histogram

<Figure size 640x480 with 1 Axes><img width="342" height="434" alt="image" src="https://github.com/user-attachments/assets/272b9b6b-d795-4032-bb03-e0d6d613c2af" />


### Final Output of Original Image and Equalized 


<Figure size 1500x400 with 2 Axes><img width="1173" height="414" alt="image" src="https://github.com/user-attachments/assets/cadaa86b-6307-4f4f-920b-357d52bec6dc" />



### Final Output of Original Image and its Histogram Equalized
<Figure size 2000x1000 with 2 Axes><img width="1246" height="372" alt="image" src="https://github.com/user-attachments/assets/d28ba237-7c7c-42dd-af81-844014f81e11" />



## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
