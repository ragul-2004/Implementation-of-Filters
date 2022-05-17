# Implementation-of-Filters
## Aim:

To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:
Import the required libraries and read the image.

### Step 2:
Convert the saved BGR image to RGB using cvtColor().

### Step 3:
Use the filters required for image smoothing and sharpening.

### Step 4:
Apply the filters using cv2.filter2D() for each respective filters.
 

### Step 5:
Plot the images of the original one and the filtered one using plt.figure() and cv2.imshow().
 

## Program:
~~~
Developed By   : RAGUL A C
Register Number: 212221240042
~~~
~~~
import cv2
import numpy as np
import matplotlib.pyplot as plt
image=cv2.imread('bike.jpg')
image2=cv2.cvtColor (image1, cv2.COLOR_BGR2RGB)
~~~
## 1. Smoothing Filters :
### i) Using Averaging Filter:
~~~
kernel1 = np.ones((11,11),np.float32)/121
avg_filter = cv2.filter2D(image2,-1,kernel1)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(avg_filter)
plt.title("Filtered")
plt.axis("off")
~~~
### ii) Using Weighted Averaging Filter:
~~~
kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
weighted_filter = cv2.filter2D(image2,-1,kernel2)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(weighted_filter)
plt.title("Filtered")
plt.axis("off")
~~~
### iii) Using Gaussian Filter:
~~~
gaussian_blur = cv2.GaussianBlur(src = image2, ksize = (11,11), sigmaX=0, sigmaY=0)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Filtered")
plt.axis("off")
~~~
### iv) Using Median Filter:
~~~
median = cv2.medianBlur(src=image2,ksize = 11)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Filtered (Median)")
plt.axis("off")
~~~
## 2. Sharpening Filters:
### i) Using Laplacian Kernal:
~~~
kernel3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
laplacian_kernel = cv2.filter2D(image2,-1,kernel3)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_kernel)
plt.title("Filtered (Laplacian Kernel)")
plt.axis("off")
~~~
### ii) Using Laplacian Operator:

~~~
laplacian_operator = cv2.Laplacian(image2,cv2.CV_64F)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_operator)
plt.title("Filtered (Laplacian Operator)")
plt.axis("off")
~~~

## Output:
### Smoothing Filters:
#### i)  Using Averaging Filter:
![output](./img/1.png)
#### ii) Using Weighted Average Filter:
![output](./img/2.png)
#### iii) Using Gaussian Filter:
![output](./img/3.png)
#### iv) Using Median Filter:
![output](./img/4.png)
### Sharpening Filters:
#### i) Using Laplacian Kernel:
![output](./img/5.png)
#### ii) Using Laplacian Operator:
![output](./img/6.png)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
