# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
## Step1:
Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

## Step2:
Read the input image using cv2.imread() and store it in a variable for further processing.

## Step3:
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

## Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

## Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.

## Program:
```
## Developed By: Iswarya P
## Register Number:212223230082
```

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
## Load the image
```
image = cv2.imread('chess.jpeg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)  # Convert BGR to RGB for Matplotlib
plt.figure(figsize=(12, 8))
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')
```
## Output:
![Screenshot 2024-10-03 101044](https://github.com/user-attachments/assets/d13e0254-b76b-4a06-8e6c-d8ccb1857ca0)

## 1. Translation
```
rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  # Translate by (50, 100) pixels
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
```
## Output:
![Screenshot 2024-10-03 101051](https://github.com/user-attachments/assets/6d6fdd5f-7206-4fef-9071-1f106dd07c01)

## 2. Scaling
```
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR)  # Scale by 1.5x
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')
```
## Output:
![Screenshot 2024-10-03 101114](https://github.com/user-attachments/assets/165d628f-809e-4f7d-a1a6-24c06fc3fbd3)

## 3. Sharing
```
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5
shared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))
plt.imshow(shared_image)
plt.title("Shared Image")
plt.axis('off')
```
## Output:
![Screenshot 2024-10-03 101134](https://github.com/user-attachments/assets/9173eb99-d16f-4cf5-9a57-cddc42363e0a)

## 4. Reflection (Flip)
```
reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')
```
## Output:
![Screenshot 2024-10-03 101141](https://github.com/user-attachments/assets/4eb45fb2-ed57-4417-8d3f-33ddc113bb42)

## 5. Rotation
```
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  # Rotate by 45 degrees
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')
```
## Output:
![Screenshot 2024-10-03 101156](https://github.com/user-attachments/assets/1aec06a8-89d9-4406-b856-53f350a07c22)

## 6. Cropping
```
cropped_image = image_rgb[50:300, 100:400]  # Crop a portion of the image
plt.figure(figsize=(4, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()
```
## Output:
![Screenshot 2024-10-03 101204](https://github.com/user-attachments/assets/6a721bb6-1b74-4fa4-94df-c35c777108ee)


## Result:

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
