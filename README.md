# EX-5 Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:

Import necessary libraries: OpenCV, NumPy, and Matplotlib.Read an image, convert it to RGB format, define an 11x11 averaging kernel, and apply 2D convolution filtering.Display the original and filtered images side by side using Matplotlib.

### Step 2:
</br>
Define a weighted averaging kernel (kernel2) and apply 2D convolution filtering to the RGB image (image2).Display the resulting filtered image (image4) titled 'Weighted Averaging Filtered' using Matplotlib's imshow function.
</br> 

### Step 3:
</br>
Apply Gaussian blur with a kernel size of 11x11 and standard deviation of 0 to the RGB image (image2).Display the resulting Gaussian-blurred image (gaussian_blur) titled 'Gaussian Blurring Filtered' using Matplotlib's imshow function.
</br> 

### Step 4:
</br>
Apply median blur with a kernel size of 11x11 to the RGB image (image2).Display the resulting median-blurred image (median) titled 'Median Blurring Filtered' using Matplotlib's imshow function.
</br> 

### Step 5:
</br>
Define a Laplacian kernel (kernel3) and perform 2D convolution filtering on the RGB image (image2).Display the resulting filtered image (image5) titled 'Laplacian Kernel' using Matplotlib's imshow function.
</br> 

### Step 6:

Apply the Laplacian operator to the RGB image (image2) using OpenCV's cv2.Laplacian function.Display the resulting image (new_image) titled 'Laplacian Operator' using Matplotlib's imshow function.

## Program:
### Developed By   : NAVEEN.S
### Register Number: 212223240106
</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('img1.jpeg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel = np.ones((11,11), np. float32)/121
image3 = cv2.filter2D(image2, -1, kernel)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title('Orignal')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')
```
ii) Using Weighted Averaging Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('img1.jpeg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image4 = cv2.filter2D(image2, -1, kernel2)
plt.imshow(image4)
plt.title('Weighted Averaging Filtered')

```
iii) Using Gaussian Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('img1.jpeg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

gaussian_blur = cv2.GaussianBlur(src=image2, ksize=(11,11), sigmaX=0, sigmaY=0)
plt.imshow(gaussian_blur)
plt.title(' Gaussian Blurring Filtered')

```
iv)Using Median Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('img1.jpeg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

median=cv2.medianBlur (src=image2, ksize=11)
plt.imshow(median)
plt.title(' Median Blurring Filtered')

```

### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('img1.jpeg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel3 = np.array([[0,1,0], [1, -4,1],[0,1,0]])
image5 =cv2.filter2D(image2, -1, kernel3)
plt.imshow(image5)
plt.title('Laplacian Kernel')

```
ii) Using Laplacian Operator
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('img1.jpeg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

new_image = cv2.Laplacian (image2, cv2.CV_64F)
plt.imshow(new_image)
plt.title('Laplacian Operator')

```

## OUTPUT:
### 1. Smoothing Filters
</br>

i) Using Averaging Filter
![Screenshot 2024-10-02 173112](https://github.com/user-attachments/assets/3f59377d-814d-49b1-a127-e9b45a7e2184)


ii)Using Weighted Averaging Filter
![Screenshot 2024-10-02 173119](https://github.com/user-attachments/assets/a83f56f0-d7bd-4b7e-b4e8-f0f88a3ac6e1)


iii)Using Gaussian Filter
![Screenshot 2024-10-02 173126](https://github.com/user-attachments/assets/91c6543a-0c26-491a-af75-37949e1d3d0d)


iv) Using Median Filter
![Screenshot 2024-10-02 173134](https://github.com/user-attachments/assets/2b10f9e4-e810-44e7-945d-eed0adbf5091)


### 2. Sharpening Filters
</br>

i) Using Laplacian Kernal
![Screenshot 2024-10-02 173140](https://github.com/user-attachments/assets/8e131df4-b7b3-48b8-91aa-d0275035f8f9)


ii) Using Laplacian Operator
![Screenshot 2024-10-02 173159](https://github.com/user-attachments/assets/5b9e312c-b63c-4da3-9e9a-c4d8081b1818)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
