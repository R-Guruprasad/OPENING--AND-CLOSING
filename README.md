# OPENING--AND-CLOSING
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step-1:Read the Image:
Load the input color image from a specified path.

### Step-2:Convert to Grayscale:
Transform the color image into a grayscale format for easier processing.

### Step-3:Edge Detection:
Apply an edge detection technique to identify the prominent edges in the grayscale image.

### Step-4:Create Structuring Element:
Define a kernel (structuring element) for use in morphological operations, typically a matrix of ones.

### Step-6:Morphological Operations:
Perform morphological operations:<br>
Opening: Remove small objects from the edges to clean up the image.<br>
Closing: Fill small holes in the detected edges to enhance the structure.

### Step-7:Display Results:
Show the original grayscale image, along with the results of the opening and closing operations for visual comparison.

## Program:

``` Python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 1: Create a blank image
image = np.zeros((300, 600, 3), dtype="uint8")

# Step 2: Create the text using cv2.putText
text = "GURU PRASAD"
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, text, (50, 150), font, 2, (255, 255, 255), 3)

# Step 3: Create a structuring element (5x5 rectangular)
kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (5, 5))

# Step 4: Use Opening operation (erosion followed by dilation)
opening_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)

# Step 5: Use Closing operation (dilation followed by erosion)
closing_image = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)

# Convert images from BGR to RGB for Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
opening_image_rgb = cv2.cvtColor(opening_image, cv2.COLOR_BGR2RGB)
closing_image_rgb = cv2.cvtColor(closing_image, cv2.COLOR_BGR2RGB)

# Plot the original, opening, and closing images using Matplotlib
plt.figure(figsize=(10, 5))

plt.subplot(1, 3, 1)
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 3, 2)
plt.imshow(opening_image_rgb)
plt.title("Opening Operation")
plt.axis("off")

plt.subplot(1, 3, 3)
plt.imshow(closing_image_rgb)
plt.title("Closing Operation")
plt.axis("off")

plt.tight_layout()
plt.show()


```
## Output:

### Display the input Image

![image](https://github.com/user-attachments/assets/3575a900-c82f-4b25-9003-5f7133b606df)

### Display the result of Opening

![image](https://github.com/user-attachments/assets/dbda48b7-4ccf-420b-9b9e-7a5283f2e73a)

### Display the result of Closing

![image](https://github.com/user-attachments/assets/995dcfe8-84d2-42cc-9fa5-fd5c10490426)


## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
