# EX-08:THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step-1:Import Libraries:

Import the necessary libraries for image processing and visualization.
### Step-2:Read and Convert Image:

Load the image from a file.
Convert the image to grayscale for better analysis.
### Step-3:Apply Global Thresholding:

Perform global thresholding on the grayscale image using a fixed threshold value.
Display the resulting binary image.
### Step-4:Apply Adaptive Thresholding:

Perform adaptive thresholding on the grayscale image to account for varying lighting conditions.
Display the resulting binary image.
### Step-5:Apply Otsu's Thresholding:

Use Otsu's method to automatically determine the optimal threshold value for segmentation.
Display the resulting binary image.
### Step-6:Compare Results:

Review and compare the segmented images from each thresholding method to evaluate which one provides the best segmentation for the specific image.
>

## Program
```
Developed By: HARI PRASATH S
Reference Number: 212222240034
```
# Load the necessary packages
```
import cv2
import matplotlib.pyplot as plt
```

# Read the Image and convert to grayscale
```
image = cv2.imread('ani.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.xticks([]), plt.yticks([])
plt.show()
```
![alt text](image.png)
# Use Global thresholding to segment the image
```
ret_global, th_global = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)
plt.imshow(th_global, cmap='gray')
plt.title('Global Thresholding (v=127)')
plt.xticks([]), plt.yticks([])
plt.show()
```
![alt text](image-1.png)

# Use Adaptive thresholding to segment the image
```
th_adaptive = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY, 11, 2)
plt.imshow(th_adaptive, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.xticks([]), plt.yticks([])
plt.show()
```
![alt text](image-2.png)

# Use Otsu's method to segment the image 
```
ret_otsu, th_otsu = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)
plt.imshow(th_otsu, cmap='gray')
plt.title("Otsu's Thresholding")
plt.xticks([]), plt.yticks([])
plt.show()
```
![alt text](image-3.png)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
