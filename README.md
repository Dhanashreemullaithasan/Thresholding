# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:

Improt the packages.

### Step2:

convert to grayscale.

### Step3:

Use global thresholding techniques.

### Step4:

Use adaptive thresholding and otsu's method.

### Step5:

Display the results using loop.

## Program

```python
# Load the necessary packages
import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale

image=cv2.imread('thers.jpg')
image1=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
plt.imshow(image1)

# Use Global thresholding to segment the image
ret,thresh_img1=cv2.threshold(image1,80,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image1,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image1,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image1,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image1,100,255,cv2.THRESH_TRUNC)



# Use Adaptive thresholding to segment the image

ret,thresh_img6=cv2.threshold(image1,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)


# Use Otsu's method to segment the image 

thresh_img7=cv2.adaptiveThreshold(image1,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image1,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image1,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()

```
## Output

### Original Image
![ex9 dip oi](https://github.com/Dhanashreemullaithasan/Thresholding/assets/94165415/d19a9ca7-5c18-42f0-b831-9ca5c42e4933)


### Global Thresholding

![ex9 dip no2](https://github.com/Dhanashreemullaithasan/Thresholding/assets/94165415/fc2937dd-45e8-4bd9-9086-c0516d7d1579)

![ex9 dip no22](https://github.com/Dhanashreemullaithasan/Thresholding/assets/94165415/181a5acf-b721-4684-ac5b-6615334dd9dd)

![ex9 dip no23](https://github.com/Dhanashreemullaithasan/Thresholding/assets/94165415/bfa6f256-1bbe-4298-8e26-47d562555325)

![ex9 dip no24](https://github.com/Dhanashreemullaithasan/Thresholding/assets/94165415/4aa33ba6-1ffd-42da-acd9-3068531a36b1)

![ex9 dip no25](https://github.com/Dhanashreemullaithasan/Thresholding/assets/94165415/e79a052b-99e4-455a-a32a-b835fa82057c)

### Adaptive Thresholding

![ex9 dip adaptive 1](https://github.com/Dhanashreemullaithasan/Thresholding/assets/94165415/035ea372-1a12-4b51-aa5f-72f3af98a876)


### Optimum Global Thesholding using Otsu's Method



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

