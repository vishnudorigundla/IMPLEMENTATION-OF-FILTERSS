# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
Step1 :- Import the required modules.

Step2 :- Convert the image from BGR to RGB.

Step3:- Apply the required filters for the image separately.

Step4:- Plot the original and filtered image by using matplotlib.pyplot

Step5:- End the program.

## Program:
```
Developed By   : D.vishnu vardhan reddy
Register Number: 212221230023
```
</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("car.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)

kernel1 = np.ones((11,11),np.float32)/121
avg_filter = cv2.filter2D(original_image,-1,kernel1)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(avg_filter)
plt.title("Filtered")
plt.axis("off")


```
ii) Using Weighted Averaging Filter
```Python
kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
weighted_filter = cv2.filter2D(original_image,-1,kernel2)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(weighted_filter)
plt.title("Filtered")
plt.axis("off")


```
iii) Using Gaussian Filter
```Python
gaussian_blur = cv2.GaussianBlur(src = original_image, ksize = (11,11), sigmaX=0, sigmaY=0)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Filtered")
plt.axis("off")


```

iv) Using Median Filter
```Python
median = cv2.medianBlur(src=original_image,ksize = 11)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Filtered")
plt.axis("off")

```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python
kernel3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
laplacian_kernel = cv2.filter2D(original_image,-1,kernel3)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_kernel)
plt.title("Filtered")
plt.axis("off")

```
ii) Using Laplacian Operator
```Python
laplacian_operator = cv2.Laplacian(original_image,cv2.CV_64F)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_operator)
plt.title("Filtered")
plt.axis("off")

```

## OUTPUT:
### 1. Smoothing Filters
</br>

i) Using Averaging Filter
</br>
![image](https://github.com/vishnudorigundla/IMPLEMENTATION-OF-FILTERSS/assets/94175324/e9aa4452-ab12-4468-b734-5cf951749e95)

</br>

ii) Using Weighted Averaging Filter
</br>
![image](https://github.com/vishnudorigundla/IMPLEMENTATION-OF-FILTERSS/assets/94175324/f63cee35-532d-4280-9262-f881031ce074)

</br>

iii) Using Gaussian Filter
</br>
![image](https://github.com/vishnudorigundla/IMPLEMENTATION-OF-FILTERSS/assets/94175324/96f12b89-8d83-45e1-929a-6c6946a999d9)

</br>

iv) Using Median Filter
</br>
![image](https://github.com/vishnudorigundla/IMPLEMENTATION-OF-FILTERSS/assets/94175324/d855e659-d148-405a-8323-8e8227efd40e)

</br>

### 2. Sharpening Filters
</br>

i) Using Laplacian Kernal
</br>
![image](https://github.com/vishnudorigundla/IMPLEMENTATION-OF-FILTERSS/assets/94175324/f792c4a2-fc5c-44ce-976c-29e5a510b61f)
</br>

ii) Using Laplacian Operator
</br>
![image](https://github.com/vishnudorigundla/IMPLEMENTATION-OF-FILTERSS/assets/94175324/4e5c5880-f44f-4e62-b2c6-c82ab826bb08)

</br>

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
