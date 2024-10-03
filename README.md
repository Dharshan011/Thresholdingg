# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program

### Developed By: DHARSHAN V
### Register No.: 212222230031
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the image
image = cv2.imread('HappyFish.jpg')

# Convert to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Display the original grayscale image
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.xticks([]), plt.yticks([])
plt.show()

```
![Screenshot 2024-10-03 161618](https://github.com/user-attachments/assets/2d4cafe7-8bcd-4dfe-ae00-a560a127a5ab)


# Global thresholding
```
ret_global, th_global = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Display the global thresholding result
plt.imshow(th_global, cmap='gray')
plt.title('Global Thresholding (v=127)')
plt.xticks([]), plt.yticks([])
plt.show()

```
![Screenshot 2024-10-03 161623](https://github.com/user-attachments/assets/64e82bb0-c044-4244-a87b-da44b46a1463)



# Adaptive thresholding (Gaussian)
```
th_adaptive = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
                                    cv2.THRESH_BINARY, 11, 2)

# Display the adaptive thresholding result
plt.imshow(th_adaptive, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.xticks([]), plt.yticks([])
plt.show()
```


![Screenshot 2024-10-03 161628](https://github.com/user-attachments/assets/68dfd8fe-8d74-44ed-aec7-de95fb448cdd)

# Otsu's thresholding
```
ret_otsu, th_otsu = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Display the Otsu thresholding result
plt.imshow(th_otsu, cmap='gray')
plt.title("Otsu's Thresholding")
plt.xticks([]), plt.yticks([])
plt.show()
```


![Screenshot 2024-10-03 161633](https://github.com/user-attachments/assets/3cee6c1a-8886-45a8-9f3e-0045d20f6af3)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
