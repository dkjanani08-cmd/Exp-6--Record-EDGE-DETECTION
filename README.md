# Exp-6--Record-EDGE-DETECTION
# NAME : D . Janani 
# REG NO : 212225040142


## Aim

To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Import all the necessary modules for the program.

### Step 2
Load an image using the `cv2.imread()` function.

### Step 3
Convert the image into grayscale using `cv2.cvtColor()`.

### Step 4
Use the Sobel operator from OpenCV to detect the edges of the image in the horizontal and vertical directions.

### Step 5
Use the Laplacian operator to detect edges based on second-order derivatives.

### Step 6
Use the Canny operator to detect edges in the image.

### Step 7
Display the edge-detected images using Matplotlib.

## Program

**Developed By:** JANANI D

**Register Number:** 212225040142

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('sv.jpeg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')

laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')

canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')  
```

## Output

### Input Image 

<img width="252" height="452" alt="image" src="https://github.com/user-attachments/assets/cfd83d98-d67a-45ec-882d-f43087f8afd7" />


### 1. Sobel Edge Detector

<img width="240" height="457" alt="image" src="https://github.com/user-attachments/assets/0a10d326-fefd-4cd1-9b9e-1a385f3fa002" />


### 2. Laplacian Edge Detector

<img width="267" height="465" alt="image" src="https://github.com/user-attachments/assets/134378e8-991f-4269-b9c4-3c7e66013bd3" />



### 3. Canny Edge Detector

<img width="257" height="447" alt="image" src="https://github.com/user-attachments/assets/34af6bf0-82a7-48e4-9cb5-7486511698cb" />


## Result

Thus, the edges of the image were detected successfully using Sobel, Laplacian, and Canny edge detectors with OpenCV and Python.
