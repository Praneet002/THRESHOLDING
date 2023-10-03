# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
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

## Program

```python
## Developed by:Gumma Dileep Kumar
## Register No: 212222240032
```

### Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

### Read the Image and convert to grayscale
```python
image = cv2.imread("ntr.jpeg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("ntr.jpeg",0)
```

### Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```

### Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```

### Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```

### Display the results
```python
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

![Screenshot from 2023-10-03 09-46-04](https://github.com/Gchethankumar/THRESHOLDING/assets/118348224/b008c8c2-bdb9-433f-935f-21f2bdf3f98c)


### Global Thresholding

![Screenshot from 2023-10-03 09-46-13](https://github.com/Gchethankumar/THRESHOLDING/assets/118348224/12620b85-d6cd-4881-a10f-def10c3bfa46)

![Screenshot from 2023-10-03 09-46-21](https://github.com/Gchethankumar/THRESHOLDING/assets/118348224/3c497c71-e4d8-4931-8d97-bf8450c3dd10)

![Screenshot from 2023-10-03 09-46-28](https://github.com/Gchethankumar/THRESHOLDING/assets/118348224/0a36c4d1-ad78-435e-8578-f94c4f7294aa)

![Screenshot from 2023-10-03 09-46-33](https://github.com/Gchethankumar/THRESHOLDING/assets/118348224/e5331fce-31c0-447f-a8da-530280165f92)

![Screenshot from 2023-10-03 09-46-40](https://github.com/Gchethankumar/THRESHOLDING/assets/118348224/f75c3232-95b3-443b-b917-cdfecb719b72)



### Adaptive Thresholding

![Screenshot from 2023-10-03 09-46-44](https://github.com/Gchethankumar/THRESHOLDING/assets/118348224/6c84e572-46c6-4c20-8d1e-e3289019602a)

![Screenshot from 2023-10-03 09-46-50](https://github.com/Gchethankumar/THRESHOLDING/assets/118348224/5ba57d36-b2a3-4120-9b1a-6001a12db22f)


### Optimum Global Thesholding using Otsu's Method

![Screenshot from 2023-10-03 09-46-57](https://github.com/Gchethankumar/THRESHOLDING/assets/118348224/f3fc10f3-c608-44e4-b611-19695a00124a)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

