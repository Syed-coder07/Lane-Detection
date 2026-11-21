## Lane-Detection

## Aim:

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

## Learning Objective:

* Understand each stage of image processing
* Learn how to build a complete computer vision pipeline
* Practice writing code in guided sections

* Important Instruction: 👉 Write code ONLY in places marked as 
                         👉 Do NOT modify any other part of the code

## Software Used:

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

## Program:

## Developed by: Syed Shamsheer Ali
## Register number:

## Step 1: Import Libraries

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

## Step 2: Import image

```
image = cv2.imread(r"C:\Users\syedf\OneDrive\Documents\DIPT\Syed1.png")
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title("Input Image")
plt.axis('off')
plt.show()
```

## Step 3: Convert to Grayscale

```
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```

## Step 4: Convert to Canny Edge Detector:

```
edges = cv2.Canny(gray_image, 50, 150) 
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```

## Step 5: Result of Hough Transform:

```
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100,
                        minLineLength=50, maxLineGap=10)

for line in lines:
    x1, y1, x2, y2 = line.reshape(4)
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Result of Hough Transform")
plt.axis('off')
```

## Output:

## Input Image:

<img width="361" height="512" alt="image" src="https://github.com/user-attachments/assets/d0e32d71-8fbf-4c62-8002-efdb3d05a8cf" />

## Grayscale image:

<img width="367" height="490" alt="image" src="https://github.com/user-attachments/assets/7554512b-dc88-42d3-9072-f4217e46c0ef" />

## Canny Edge Detector Image:

<img width="368" height="495" alt="image" src="https://github.com/user-attachments/assets/1d9ac839-1f67-4965-a61f-8ecf5722c7b3" />

## Result of Hough Transform:

<img width="363" height="497" alt="image" src="https://github.com/user-attachments/assets/f294a759-b505-4cd4-a617-8eec74446612" />

## Result:

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.
