# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the necessary modules and read the image.
### Step2
Perform linear filtering operation.
### Step3
Apply following filters to the image for smoothing:

1. Averaging filter
2. Weighted Averaging Filter
3. Gaussian Blur
4. Median filter
### Step4
Apply following filters to the image for sharpening:

1. Laplacian kernel
2. Laplacian operator

### Step5
Display the image after applying filters.

```
Developed By : Y SHAVEDHA
Register Number : 212221230095
```
### Importing Libraries
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('eif3.jpg')
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
```
### 1. Smoothing Filters

i) Using Averaging Filter
```
#Averaging filter
kernel1 = np.ones((11,11),np.float32)/121
avg_filter = cv2.filter2D(original_image,-1,kernel1)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(avg_filter)
plt.title("Filtered")
plt.axis("off")
```
ii) Using Weighted Averaging Filter
```
#Weighted Averaging Filter
kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
weighted_filter = cv2.filter2D(original_image,-1,kernel2)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(weighted_filter)
plt.title("Filtered")
plt.axis("off")
```
iii) Using Gaussian Filter
```
# Gaussian Filter
gaussian_blur = cv2.GaussianBlur(src=original_image,ksize=(11,11), sigmaX=0,sigmaY=0)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Filtered")
plt.axis("off")
```

iv) Using Median Filter
```
#Median Filter
median = cv2.medianBlur(src=original_image,ksize=11)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blurring")
plt.axis("off")
```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```
# SHARPENING FILTERS
# Laplacian kernal
kernal3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
l_kernal = cv2.filter2D(original_image,-1,kernal3)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(l_kernal)
plt.title("laplacian kernal")
plt.axis("off")
```
ii) Using Laplacian Operator
```
#using laplacian operator
l_operator = cv2.Laplacian(original_image,cv2.CV_64F)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(l_operator)
plt.title("Laplacian Operator")
plt.axis("off")
```

## OUTPUT:
### 1. Smoothing Filters
</br>

i) Using Averaging Filter

<img width="702" alt="image" src="https://user-images.githubusercontent.com/93427376/230822679-e5ffe313-1907-40e2-804b-bf162f6428b4.png">

ii) Using Weighted Averaging Filter

<img width="675" alt="image" src="https://user-images.githubusercontent.com/93427376/230822718-8897f0a0-aa56-416e-868f-1e5548131b2b.png">


iii) Using Gaussian Filter

<img width="658" alt="image" src="https://user-images.githubusercontent.com/93427376/230822754-8d45d6d7-c8df-4f1b-99dd-06aafd572c87.png">


iv) Using Median Filter

<img width="654" alt="image" src="https://user-images.githubusercontent.com/93427376/230822784-9175d3e5-3c7a-45f1-8061-fb4ff73a31ed.png">


### 2. Sharpening Filters
</br>

i) Using Laplacian Kernal

<img width="673" alt="image" src="https://user-images.githubusercontent.com/93427376/230822821-d0e83125-3451-431d-ad04-ed2a240d6445.png">

ii) Using Laplacian Operator

<img width="643" alt="image" src="https://user-images.githubusercontent.com/93427376/230822848-535bd6ee-90a7-495d-bc8f-5022264105f4.png">


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
