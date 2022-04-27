# Histogram and Histogram Equalization of an image
## AIM:
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## SOFTWARE REQUIRED:
Anaconda - Python 3.7

## ALGORITHM:
### Step 1:
Import the necessary libraries and read two images, Color image and Gray Scale image.
### Step 2:
Calculate the Histogram of Gray scale image and any one channel of the color image.
### Step 3:
Display the histograms.
### Step 4:
Equalize the grayscale image.
### Step 5:
Display the equalized grayscale image.

## Program:
```python
# Developed By: Dinesh.S
# Register Number: 212220230011

import cv2
import matplotlib.pyplot as plt
Gray_image=cv2.imread('Parrot.jpg')
plt.imshow(Gray_image)
plt.show()
Color_image=cv2.imread('Heidi.jpg')
plt.imshow(Color_image)
plt.show()

# Write your code to find the histogram of gray scale image and color image channels.

hist = cv2.calcHist([Gray_image],[0],None,[256],[0,256])
plt.figure()
plt.title("Histogram")
plt.xlabel('gray_scale value')
plt.ylabel('pixel count')
plt.stem(hist)
plt.show()

# Display the histogram of gray scale image and any one channel histogram from color image

hist1 = cv2.calcHist([Color_image],[0],None,[256],[0,256])
plt.figure()
plt.title("Histogram")
plt.xlabel('color_scale value')
plt.ylabel('pixel count')
plt.stem(hist1)
plt.show()

# Write the code to perform histogram equalization of the image. 

equ=cv2.equalizeHist(cv2.imread('Heidi.jpg',0))
equ=cv2.cvtColor(equ,cv2.COLOR_BGR2RGB)
plt.title("Equalised Image")
plt.axis("off")
plt.imshow(equ)
plt.show()

```
## Output:
### Input Grayscale Image and Color Image

![DIP41](https://user-images.githubusercontent.com/75235813/165233378-17a48db5-f446-4cd6-a914-bba050121544.JPG)
![DIP42](https://user-images.githubusercontent.com/75235813/165233395-d7054904-c953-4548-8d1b-2ff083b62fb0.JPG)



### Histogram of Grayscale Image and any channel of Color Image

![DIP43](https://user-images.githubusercontent.com/75235813/165233415-1f71763c-d0de-47d0-adda-cb6deecd5ca0.JPG)
![DIP44](https://user-images.githubusercontent.com/75235813/165233438-26f64c9b-8479-4223-a501-9ef3ba69e83c.JPG)


### Histogram Equalization of Grayscale Image

![DIP45](https://user-images.githubusercontent.com/75235813/165233458-df2978d9-51d5-4cf8-b076-a58c51f3cce8.JPG)


## Result:

Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
