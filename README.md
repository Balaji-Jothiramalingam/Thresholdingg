# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

## Step1:
Load the necessary packages.
## Step2:
Read the Image and convert to grayscale.
### Step3:
Use Global thresholding to segment the image.
## Step4:
Use Adaptive thresholding to segment the image.
## Step5:
Use Otsu's method to segment the image and display the results.


## Program
DEVELOPED BY:BALAJI J
REGISTER NO:212221243001
# Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```




# Read the Image and convert to grayscale
```
image = cv2.imread('kitty.jpeg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('kitty.jpeg',0)
```



# Use Global thresholding to segment the image

```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

```


# Use Adaptive thresholding to segment the image


```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```

# Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```



# Display the results


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

![327146408-90916955-39cd-46a8-9334-7e0dca43f3a1](https://github.com/user-attachments/assets/b0f95aba-6e02-41f4-929c-6ba2df9ba593)


### Global Thresholding

![327146636-5c95cd81-7b56-4db0-bcaa-45837cb935b5](https://github.com/user-attachments/assets/dc63dc30-073e-49da-aa25-04928b80bb9d)





![327146760-ad092623-ed88-4235-947a-eaa6e1a42158](https://github.com/user-attachments/assets/0cf0624d-88f0-4b2a-8f1d-3c92d4177dd8)






### Adaptive Thresholding

![327147478-436d3d17-6cca-4b6f-8131-3f483e79b6bc](https://github.com/user-attachments/assets/321a753c-b188-437e-8a10-915413cd96a7)




### Optimum Global Thesholding using Otsu's Method

![327148240-004d1d9b-a6ef-44e8-b746-54874d0ace04](https://github.com/user-attachments/assets/f7f6d4be-cf16-4195-8c7f-ae0bceaeb876)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
