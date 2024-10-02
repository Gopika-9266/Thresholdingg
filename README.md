# THRESHOLDING
## Aim:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required:
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm:

### Step 1:
Load the necessary packages.
### Step 2:
Read the Image and convert to grayscale
### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:

Use Otsu's method to segment the image and display the results.

## Program:
```
Developed By: Gopika R
Register Number: 212222240031
```

### Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```
image = cv2.imread('seoul.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('seoul.jpg',0)
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
## Output:

### Original Image
![Screenshot 2024-10-02 110422](https://github.com/user-attachments/assets/79f72822-183d-42f8-8cb5-c7915225db40)


### Global Thresholding

![Screenshot 2024-10-02 110456](https://github.com/user-attachments/assets/366891a8-14be-4eba-a448-656c27342ba6)

![Screenshot 2024-10-02 110516](https://github.com/user-attachments/assets/2f925fc8-952a-40f2-937a-bcae0417e33b)

![Screenshot 2024-10-02 110529](https://github.com/user-attachments/assets/8bf2d924-d144-4012-9151-ef3a9ccac237)

![Screenshot 2024-10-02 110546](https://github.com/user-attachments/assets/2e488cef-2a24-46d3-9507-00affe49443c)

![Screenshot 2024-10-02 110602](https://github.com/user-attachments/assets/6ea40a63-f78b-4361-9956-0767c3b4ca30)

### Adaptive Thresholding

![Screenshot 2024-10-02 110646](https://github.com/user-attachments/assets/8ee6421e-a5da-4505-881d-b3845827c231)

![Screenshot 2024-10-02 110704](https://github.com/user-attachments/assets/39dae231-aae1-445f-b33e-6ad2dbc557e2)


### Optimum Global Thesholding using Otsu's Method

![Screenshot 2024-10-02 110720](https://github.com/user-attachments/assets/f1f87095-23b2-401c-a684-3e77b0384c77)


## Result:

Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
