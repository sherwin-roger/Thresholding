# Thresholding
## AIM:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## SOFTWARE REQUIRED:
1. Anaconda - Python 3.7
2. OpenCV

## ALGORITHM:

### Step 1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale.

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image.

### Step 6:
Display the results.

## PROGRAM:
```python
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("hinata.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("hinata.jpg",0)

# Use Global thresholding to segment the image
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(5,5))
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
## OUTPUT:

### Original Image and Grayscale Image
![o1](https://user-images.githubusercontent.com/75235747/169685239-93aabb61-910b-40f0-aef1-c68b38828fac.JPG)

### Global Thresholding
![o2](https://user-images.githubusercontent.com/75235747/169685264-825e6050-364d-412f-93f0-139aca6074f5.JPG)
![o3](https://user-images.githubusercontent.com/75235747/169685271-00b06c2f-4234-44bc-850f-df53aef0a04d.JPG)
![o4](https://user-images.githubusercontent.com/75235747/169685277-c6131255-4a5c-49ef-b7a3-96782a5ebb1c.JPG)
![o5](https://user-images.githubusercontent.com/75235747/169685283-fdb0689d-a640-41b2-884f-0f4be4d3dbad.JPG)
![o6](https://user-images.githubusercontent.com/75235747/169685289-52af4266-0a0d-4b05-84d6-6089ab5c5113.JPG)

### Adaptive Thresholding
![o8](https://user-images.githubusercontent.com/75235747/169685316-de7f3fc3-eeb4-48b6-bfbe-bcd0ceb5ae82.JPG)
![o9](https://user-images.githubusercontent.com/75235747/169685326-8562d567-f3d4-48b1-9529-acf81762bacd.JPG)

### Optimum Global Thesholding using Otsu's Method
![o7](https://user-images.githubusercontent.com/75235747/169685312-d9430aac-19ff-4068-92b3-a701dcd9cb44.JPG)

## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
