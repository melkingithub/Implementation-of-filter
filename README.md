# Implementation-of-filter
### Name - MELKIN SAM.D
### Register Number - 212223220056
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the required libraries.

### Step2
Convert the image from BGR to RGB.

### Step3
Apply the required filters for the image separately.

### Step4
Plot the original and filtered image by using matplotlib.pyplot.

### Step5
End the program.

## Program:



### 1. Smoothing Filters

#### i) Using Averaging Filter
```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("/content/Grass.png")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```
## Output
<img width="961" height="310" alt="image" src="https://github.com/user-attachments/assets/1f5f5df1-03c0-4412-916e-b219dacb9c2f" />


#### ii) Using Weighted Averaging Filter
```
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
## Output
<img width="650" height="434" alt="image" src="https://github.com/user-attachments/assets/10baf564-0bb0-428b-a6e7-d489da786c63" />


#### iii) Using Gaussian Filter
```
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```
## Output
<img width="667" height="443" alt="image" src="https://github.com/user-attachments/assets/a7a31e14-fd48-4c1e-8463-fd3761ea1270" />

#### iv)Using Median Filter
```
median=cv2.medianBlur(image2,13)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```
## Output
<img width="617" height="375" alt="image" src="https://github.com/user-attachments/assets/40c7ae36-e13a-4122-ad9b-4903a671fa96" />

### 2. Sharpening Filters

#### i) Using Laplacian Linear Kernal
```
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
## Output
<img width="660" height="424" alt="image" src="https://github.com/user-attachments/assets/a9a6e190-731c-4fad-9234-fde79e4b29bf" />

#### ii) Using Laplacian Operator
```
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```
## Output
<img width="694" height="429" alt="image" src="https://github.com/user-attachments/assets/7e6b1292-14e8-4515-abc1-300850563f68" />


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
