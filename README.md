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
```
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("dog.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("dog.jpg",0)

# Use Global thresholding to segment the image
ret,thresh_jk1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_jk2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_jk3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_jk4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_jk5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image
thresh_jk7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_jk8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 
ret,thresh_jk6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_jk1,thresh_jk2,thresh_jk3,thresh_jk4,thresh_jk5,thresh_jk6,thresh_jk7,thresh_jk8]
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
## OUTPUT:

### Original Image and Grayscale Image
![download](https://github.com/MarellaDharanesh/Thresholding/assets/118707669/a9776988-714b-4875-bc93-6b75f5525ddd)




### Global Thresholding
![download](https://github.com/MarellaDharanesh/Thresholding/assets/118707669/74447702-3c9f-47da-97c2-731825ed59c9)

![download](https://github.com/MarellaDharanesh/Thresholding/assets/118707669/dea445fe-2ba9-4848-bafd-3bd81077570d)
![download](https://github.com/MarellaDharanesh/Thresholding/assets/118707669/2c0fabce-30bf-4fc3-8a89-4c4a43ea0f45)
![download](https://github.com/MarellaDharanesh/Thresholding/assets/118707669/1539e711-34f9-453a-9b60-d368e28a547d)

![download](https://github.com/MarellaDharanesh/Thresholding/assets/118707669/9f38b189-f4c4-4fc4-b8e3-29c21e67a0f1)


### Adaptive Thresholding
![download](https://github.com/MarellaDharanesh/Thresholding/assets/118707669/0f22a458-0d47-42e0-acf8-945d75590d2c)
![download](https://github.com/MarellaDharanesh/Thresholding/assets/118707669/a4ed595b-99fc-4df7-9726-15eec5683eb1)




### Optimum Global Thesholding using Otsu's Method
![download](https://github.com/MarellaDharanesh/Thresholding/assets/118707669/54020412-33cb-4a31-a2d6-0ca2d3eb1ae3)



## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
