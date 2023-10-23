# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Import the necessary packages.

### Step2:
Create the text using cv2.putText.

### Step3:
Create the structuring element.

### Step4:
Erode the image using cv2.erode().

### Step5:
Dilate the imge using cv2.dilate().


## Program
```
DEVELOPED BY:RASIKA.M
REGISTER NUMBER:212222230117
```

# Load the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```



# Read the Image and convert to grayscale
```
image=cv2.imread("unicorn.jpg")
plt.imshow(image)
plt.title('original image')
plt.axis('off')
gray_img=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
plt.imshow(gray_img,'gray')
plt.title('Gray image')
plt.axis('off')
```


# Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(gray_img,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(gray_img,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(gray_img,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(gray_img,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(gray_img,100,255,cv2.THRESH_TRUNC)
```


# Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(gray_img,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(gray_img,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```





# Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(gray_img,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```



# Display the results
```
titles=["Gray Image", "Threshold Image (Binary)", "Threshold Image (Binary Inverse)", "Threshold Image (To Zero)"
       , "Threshold Image (To Zero-Inverse)", "Threshold Image (Truncate)", "Otsu", "Adaptive Threshold (Mean)", "Adaptive Threshold (Gaussian)"]
images=[gray_img, thresh_img1, thresh_img2, thresh_img3, thresh_img4, thresh_img5, thresh_img6, thresh_img7, thresh_img8] 

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
## Output

### Original Image
![Screenshot from 2023-10-23 10-26-03](https://github.com/rasika1206/THRESHOLDING/assets/124434806/0482c1f4-dc7b-4475-ac23-75d562b5488e)

<br>
<br>
<br>
<br>
<br>

### Global Thresholding
![Screenshot from 2023-10-23 10-27-23](https://github.com/rasika1206/THRESHOLDING/assets/124434806/ce0a09f2-e696-457e-8692-851a90d7be41)
![Screenshot from 2023-10-23 10-27-44](https://github.com/rasika1206/THRESHOLDING/assets/124434806/2ae814f9-6d9f-4ddb-8e8e-4e368e44b2f6)

<br>
<br>
<br>
<br>
<br>

### Adaptive Thresholding
![Screenshot from 2023-10-23 10-28-09](https://github.com/rasika1206/THRESHOLDING/assets/124434806/f11f77fb-5cfa-418b-801b-9b02df74850d)


### Optimum Global Thesholding using Otsu's Method
<br>![Screenshot from 2023-10-23 10-28-25](https://github.com/rasika1206/THRESHOLDING/assets/124434806/c72a3a55-46c0-412b-9003-a9e8c75db743)




## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

