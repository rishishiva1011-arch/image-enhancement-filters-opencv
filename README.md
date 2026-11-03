# Image Smoothing and Sharpening Using OpenCV

## Aim

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

---

## The program performs the following operations:

- Read and display an input image  
- Apply Averaging filter  
- Apply Weighted Averaging filter  
- Apply Gaussian filter  
- Apply Median filter  
- Apply Laplacian sharpening using kernel  
- Apply Laplacian operator  
- Display all outputs for comparison  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image (e.g., `image.jpg`).

### Step 3:
Convert the image from BGR to RGB format for display.

### Step 4:
Apply Averaging Filter using `cv2.blur()`.

### Step 5:
Apply Weighted Averaging Filter using a custom kernel with `cv2.filter2D()`.

### Step 6:
Apply Gaussian Filter using `cv2.GaussianBlur()`.

### Step 7:
Apply Median Filter using `cv2.medianBlur()`.

### Step 8:
Apply Laplacian Sharpening using Kernel with `cv2.filter2D()`.

### Step 9:
Convert image to grayscale and apply Laplacian Operator using `cv2.Laplacian()`.

### Step 10:
Display all filtered images using a grid layout for comparison.

---

##  Developed By

- **Name:** Rishikesh S
- **Register No:** 212225240118

---

## Program

## 1. Smoothing Filters
## i) Using Averaging Filter
```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("Hot Air.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```


## ii) Using Weighted Averaging Filter
```
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```


## iii) Using Gaussian Filter
```
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```


## iv)Using Median Filter
```
median=cv2.medianBlur(image2,13)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```


## 2. Sharpening Filters
## i) Using Laplacian Linear Kernal
```
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```


## ii) Using Laplacian Operator
```
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```


## Output
### Smoothing Filters

- Averaging filter produces blurred image

  <img width="1095" height="666" alt="image" src="https://github.com/user-attachments/assets/f70b7bc7-8bab-42f5-92d2-cad52129d0c5" />

  <br>
  
- Weighted averaging provides smoother result with less distortion

  <img width="1563" height="963" alt="image" src="https://github.com/user-attachments/assets/03dcb732-1ad2-43ab-9641-4a82f9964db0" />

  <br>

- Gaussian filter preserves edges better while reducing noise

  <img width="1557" height="945" alt="image" src="https://github.com/user-attachments/assets/fb0a1f47-4a53-4794-898a-288bc43cf7ef" />

  <br>
  
- Median filter removes salt-and-pepper noise effectively  

  <img width="2145" height="1278" alt="image" src="https://github.com/user-attachments/assets/e3126885-55d1-4232-ad87-f40ad9f7851c" />

  <br>
  
###  Sharpening Filters

- Laplacian kernel enhances edges and fine details

  <img width="1566" height="936" alt="image" src="https://github.com/user-attachments/assets/97d1d281-f615-4f56-913f-bfcf3b40ee05" />

  <br>
  
- Laplacian operator detects edges clearly in grayscale

  <img width="1542" height="936" alt="image" src="https://github.com/user-attachments/assets/2b19de59-6d6f-4d1d-a615-e1be7e70d136" />

  <br>

---



##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
