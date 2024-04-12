# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import necessary packages

### Step2:
Create an empty window and add text to it

### Step3:
create a structuring element

### Step4:
Do the operation

### Step5:
Print the output images

 
## Program:

``` Python
import cv2
import numpy as np
from matplotlib import pyplot as plt

#to read the color image
input_image_path='dog.jpg'
color_image=cv2.imread(input_image_path)

#convert the color image to grayscale
gray_image=cv2.cvtColor(color_image,cv2.COLOR_BGR2GRAY)

#perform edge detection using Canny
edges=cv2.Canny(gray_image,100,200)

#define the kernel size for erosion and dilation
kernel_size=5
kernel=np.ones((kernel_size,kernel_size),np.uint8)

#perform erosion
erosion=cv2.erode(edges,kernel,iterations=1)

#perform dilation
dilation=cv2.dilate(edges,kernel,iterations=1)

#display all images
plt.figure(figsize=(15,10))

plt.subplot(2,3,1)
plt.imshow(cv2.cvtColor(color_image,cv2.COLOR_BGR2RGB))
plt.title('Original Color Image')
plt.axis('on')

plt.subplot(2,3,2)
plt.imshow(gray_image,cmap='gray')
plt.title('Black and White Image')
plt.axis('on')

plt.subplot(2,3,3)
plt.imshow(edges,cmap='gray')
plt.title('Edge Segmentation')
plt.axis('on')

plt.subplot(2,3,4)
plt.imshow(erosion,cmap='gray')
plt.title('Erosion')
plt.axis('on')

plt.subplot(2,3,5)
plt.imshow(dilation,cmap='gray')
plt.title('Dilation')
plt.axis('on')

plt.show()


```
## Output:

### Display the input Image
![image](https://github.com/Safeeq-Fazil/erosion-dilation/assets/118680361/f83f9226-f817-4be9-8121-d1af8bba6190)

### Display the Eroded Image
![image](https://github.com/Safeeq-Fazil/erosion-dilation/assets/118680361/e4d3353c-776e-43be-b637-1c98ae8f5c92)


### Display the Dilated Image
![image](https://github.com/Safeeq-Fazil/erosion-dilation/assets/118680361/e56b132d-f10d-4b1a-a2b8-9a876a813b57)

### Final Output:
![image](https://github.com/Safeeq-Fazil/erosion-dilation/assets/118680361/bdb2b556-f6e2-4b2b-836b-9cd8f708f354)

## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
