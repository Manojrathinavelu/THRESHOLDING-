# EX-08 THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Load the necessary packages.
### Step2:
Read the Image and convert to grayscale.
### Step3:
Use Global thresholding to segment the image.
### Step4:
Use Adaptive thresholding to segment the image.
### Step5:
Use Otsu's method to segment the image and display the results.
## Program
```
DEVELOPED BY:MANOJ KARTHIK R
REGISTER NO: 212222240061
```
### Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```
image = cv2.imread("captain.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("captain.jpg",0)
```
### Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
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
![image](https://github.com/Manojrathinavelu/THRESHOLDING-/assets/119560395/358183ec-2bd1-4079-906a-dcd1364d4c8d)


### Global Thresholding
![image](https://github.com/Manojrathinavelu/THRESHOLDING-/assets/119560395/93e77bf7-a71d-4afb-9575-cc9b12dfde0c)
![image](https://github.com/Manojrathinavelu/THRESHOLDING-/assets/119560395/083c0b4f-d8d5-40e4-ae77-3799cc7d8691)
![image](https://github.com/Manojrathinavelu/THRESHOLDING-/assets/119560395/365be89a-12f7-4b9d-b469-b4dbe4c19c58)
![image](https://github.com/Manojrathinavelu/THRESHOLDING-/assets/119560395/bbd0bb69-c77f-45a8-9046-bc10b7576e12)
![image](https://github.com/Manojrathinavelu/THRESHOLDING-/assets/119560395/67019cdb-3b9c-4a30-994d-fee124a75a14)


### Adaptive Thresholding
![image](https://github.com/Manojrathinavelu/THRESHOLDING-/assets/119560395/033f756d-b496-48a7-90c7-ac205d467787)
![image](https://github.com/Manojrathinavelu/THRESHOLDING-/assets/119560395/aee2a041-0bca-40c0-958e-14c41643737f)


### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/Manojrathinavelu/THRESHOLDING-/assets/119560395/afb377e8-2b8c-4a87-82b5-1ad66892d2a8)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
