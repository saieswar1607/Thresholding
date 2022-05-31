# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:

Import required packages
<br>

### Step2:

Import the image to operate on.
<br>

### Step3:

Convert the image to grayscale image.
<br>

### Step4:

Apply threshold operators on the image.
<br>

### Step5:

Display the output.
<br>

## Program

```python
# Devleoped by:- Sai Eswar Kandukuri
# Registration number:- 212221240020
# Load the necessary packages

import cv2
import matplotlib.pyplot as plt
image = cv2.imread("goat.jpg")

# Read the Image and convert to grayscale

grayImage = cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)

# Use Global thresholding to segment the image

ret,thresh = cv2.threshold(grayImage,100,200,cv2.THRESH_BINARY)
ret1,thresh1 = cv2.threshold(grayImage,100,200,cv2.THRESH_BINARY_INV)
ret2, thresh2 = cv2.threshold(grayImage,100,200,cv2.THRESH_TRUNC)
ret3, thresh3 = cv2.threshold(grayImage,100,200,cv2.THRESH_TOZERO)
ret4, thresh4 = cv2.threshold(grayImage,100,200,cv2.THRESH_TOZERO_INV)

# Use Adaptive thresholding to segment the image

th1 = cv2.adaptiveThreshold(grayImage,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
th2 = cv2.adaptiveThreshold(grayImage,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
titles = ["Original Image","Adaptive Mean Thresholding","Adaptive Gaussian Thresholding"]
imgs = [grayImage,th1,th2]

# Use Otsu's method to segment the image 

ret5,th3 = cv2.threshold(grayImage,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results

cv2.imshow("Original Image",image)
cv2.imshow("Gray Image",grayImage)
cv2.imshow("THRESH_BINARY",thresh)
cv2.imshow("THRESH_BINARY_INV",thresh1)
cv2.imshow("THRESH_TRUNC",thresh2)
cv2.imshow("THRESH_TOZERO",thresh3)
cv2.imshow("THRESH_TOZERO_INV",thresh4)

for i in range(3):
    plt.subplot(3,1,i+1)
    plt.imshow(imgs[i],'gray')
    plt.title(titles[i])
    plt.xticks([]),plt.yticks([])
plt.show()

cv2.imshow("Otsu method",th3)
```
## Output

### Original Image

![1](https://user-images.githubusercontent.com/93427011/169686690-8757051a-edc6-41c4-ab2c-2b02932ef1d5.jpeg)
![2](https://user-images.githubusercontent.com/93427011/169686695-8d9b49b7-918f-4e73-bd25-80c85dbbeed7.jpeg)


### Global Thresholding
![3](https://user-images.githubusercontent.com/93427011/169686705-83ae370c-67d6-4bb5-8f90-44c7f2de9d29.jpeg)
![4](https://user-images.githubusercontent.com/93427011/169686708-48742021-548e-4394-a750-8cd7f1ff0744.jpeg)
![5](https://user-images.githubusercontent.com/93427011/169686714-f522ed81-796d-459e-900c-7fcc7c61e03d.jpeg)
![6](https://user-images.githubusercontent.com/93427011/169686716-a6910cab-1440-4279-bac8-a116cdea6ddf.jpeg)
![7](https://user-images.githubusercontent.com/93427011/169686719-9d1c80d4-49f0-49c7-aa3a-b4660bac818b.jpeg)


### Adaptive Thresholding

<img width="246" alt="9" src="https://user-images.githubusercontent.com/93427011/169686730-d29c9954-f0f3-4ccb-ab37-29ad34dad055.png">


### Optimum Global Thesholding using Otsu's Method

![8](https://user-images.githubusercontent.com/93427011/169686747-ab466843-bfb2-44c9-806c-3fd010c2c275.jpeg)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
