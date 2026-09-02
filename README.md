# Image Segmentation Using Thresholding Techniques in OpenCV

## Aim

To segment an image using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques using Python and OpenCV.

The program performs the following operations:

- Global Thresholding
- Adaptive Thresholding
- Otsu's Thresholding

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Load the input image using OpenCV.

### Step 3:

Convert the input image into grayscale format.

### Step 4: Global Thresholding

- Select a fixed threshold value.
- Apply thresholding to separate foreground and background pixels.
- Display the thresholded image.

### Step 5: Adaptive Thresholding

- Compute threshold values for small regions of the image.
- Apply Adaptive Mean Thresholding.
- Apply Adaptive Gaussian Thresholding.
- Display the segmented images.

### Step 6: Otsu's Thresholding

- Automatically determine the optimal threshold value.
- Apply Otsu's thresholding technique.
- Display the segmented image.

### Step 7:

Compare the results obtained from Global, Adaptive, and Otsu's thresholding methods.

## Program

## Developed By

**Name:** THENAMIZHTHAN V

**Register No:** 212225240175


```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 2: Read the image and convert to grayscale
image = cv2.imread('myimg.jpeg')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale


# Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')


# Step 3: Use Global Thresholding to segment the image
# Apply global thresholding with a threshold value of 127
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Step 4: Use Adaptive Thresholding to segment the image
# Apply adaptive thresholding using Gaussian method
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)


# Step 5: Use Otsu's method to segment the image
# Apply Otsu's method for optimal thresholding
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)




# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()


```
## Output

### Original Grayscale Image

- The grayscale version of the input image is displayed.
- Serves as the input for thresholding operations.

<img width="212" height="287" alt="image" src="https://github.com/user-attachments/assets/159b50a6-0c9f-4f49-b6d8-5848e1fa820f" />


### Global Thresholding

- Original image is displayed.
- Thresholded image is displayed.
- A fixed threshold value is used for segmentation.
- Pixels are classified as foreground or background.

<img width="222" height="290" alt="image" src="https://github.com/user-attachments/assets/2677c28f-1d85-4a0e-bfdc-a1f2899177d1" />


### Adaptive Thresholding

- Original image is displayed.
- Adaptive Mean Thresholded image is displayed.
- Adaptive Gaussian Thresholded image is displayed.
- Threshold values vary across different regions of the image.
- Suitable for images with uneven illumination.

<img width="258" height="298" alt="image" src="https://github.com/user-attachments/assets/a1fdcef5-00f6-4c95-bd4b-8866058082a2" />


### Otsu's Thresholding

- Original image is displayed.
- Otsu segmented image is displayed.
- Optimal threshold value is calculated automatically.
- Produces improved segmentation for bimodal histograms.

<img width="190" height="292" alt="image" src="https://github.com/user-attachments/assets/655090ca-b469-40fb-a17e-218c5de3fb2d" />



## Result

Thus, image segmentation is successfully performed using **Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding** techniques in OpenCV. # Exp-8-Record-THRESHOLDING
