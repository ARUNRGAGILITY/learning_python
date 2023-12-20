# Python Image Processing

Simple image processing can be done in Python using libraries like PIL (Python Imaging Library), which is known as `Pillow`, OpenCV, or `matplotlib` for basic operations. Here's a brief overview of how you can perform simple image processing tasks using these libraries:

### Using Pillow

Pillow is the friendly PIL fork and an easy-to-use library developed for opening, manipulating, and saving many different image file formats.

First, you need to install the library using `pip`:

```bash
pip install Pillow
```

Here's an example of how you might use Pillow to perform basic image processing tasks:

```python
from PIL import Image, ImageFilter

# Open an image file
with Image.open('path_to_image.jpg') as img:
    # Apply a filter to the image
    blurred_img = img.filter(ImageFilter.BLUR)

    # Convert the image to grayscale
    grayscale_img = img.convert('L')

    # Resize the image
    resized_img = img.resize((300, 300))

    # Rotate the image
    rotated_img = img.rotate(90)

    # Save the processed images
    blurred_img.save('blurred_image.jpg')
    grayscale_img.save('grayscale_image.jpg')
    resized_img.save('resized_image.jpg')
    rotated_img.save('rotated_image.jpg')
```

### Using OpenCV

OpenCV (Open Source Computer Vision Library) is an open-source computer vision and machine learning software library. It can perform a wide range of image and video processing operations.

To install OpenCV, run:

```bash
pip install opencv-python-headless
```

Here's a simple OpenCV example:

```python
import cv2

# Read the image
img = cv2.imread('path_to_image.jpg')

# Convert to grayscale
gray_img = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

# Blur the image
blurred_img = cv2.GaussianBlur(img, (5, 5), 0)

# Detect edges in the image
edges_img = cv2.Canny(img, 100, 200)

# Save the processed images
cv2.imwrite('gray_image.jpg', gray_img)
cv2.imwrite('blurred_image.jpg', blurred_img)
cv2.imwrite('edges_image.jpg', edges_img)
```

### Using Matplotlib

`matplotlib` is primarily used for plotting graphs, but it can also be used for basic image loading, displaying, and saving.

To install `matplotlib`, use:

```bash
pip install matplotlib
```

Here's how you can display an image using `matplotlib`:

```python
import matplotlib.pyplot as plt
import matplotlib.image as mpimg

# Load the image
img = mpimg.imread('path_to_image.jpg')

# Display the image
plt.imshow(img)
plt.show()

# Save the image
mpimg.imsave('saved_image.jpg', img)
```

### Combining with NumPy

Many image processing tasks involve converting images to NumPy arrays to facilitate complex operations. Both Pillow and OpenCV can interact with NumPy for advanced processing.

Here's a simple example using Pillow and NumPy:

```python
import numpy as np
from PIL import Image

# Open an image and convert it to a NumPy array
img = Image.open('path_to_image.jpg')
img_array = np.array(img)

# Perform operations on the array
# For example, invert the image
inverted_array = 255 - img_array

# Convert array back to an image
inverted_img = Image.fromarray(inverted_array)

# Save the processed image
inverted_img.save('inverted_image.jpg')
```

These are just basic operations. Both Pillow and OpenCV offer a wide range of functions for more complex image processing tasks like object detection, feature matching, filtering, transformations, and more.