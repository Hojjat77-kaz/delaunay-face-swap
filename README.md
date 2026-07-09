# Triangle-Based Face Swap using OpenCV

## Overview

This project implements a classical **face swapping** algorithm using **OpenCV**, **Dlib**, and **Delaunay Triangulation**.

Unlike deep learning approaches, this implementation reconstructs the source face by warping individual facial triangles onto a target face. The final result is blended naturally using OpenCV's **Seamless Cloning** technique.

---

## Features

* Face detection using Dlib
* 68-point facial landmark detection
* Delaunay triangulation
* Triangle-by-triangle affine transformation
* Convex hull face masking
* Seamless blending with OpenCV

---

## Algorithm

The face swapping pipeline consists of the following steps:

1. Detect the largest face in both images.
2. Extract the 68 facial landmarks.
3. Generate a Delaunay triangulation on the source face.
4. For each triangle:

   * Find the corresponding triangle in the destination face.
   * Compute the affine transformation.
   * Warp the source triangle to the destination image.
5. Construct a convex hull around the destination landmarks.
6. Create a facial mask from the convex hull.
7. Compute the center of the destination face.
8. Blend the reconstructed face into the destination image using `cv.seamlessClone()`.

---

## Requirements

* Python 3.10+
* OpenCV
* NumPy
* Dlib

Install the required dependencies:

```bash
pip install -r requirements.txt
```

---

## Usage

```python
source_image = cv.imread("images/source.jpg")
target_image = cv.imread("images/target.jpg")

result = face_swap(source_image, target_image)
```

---

## Results

### Source Image

*(Add source image here)*

### Target Image

*(Add target image here)*

### Face Swap Result

*(Add output image here)*

---

## Technologies

* Python
* OpenCV
* Dlib
* NumPy

---

## Future Improvements

* Real-time video face swapping
* Multiple-face support
* Face alignment
* Automatic color correction
* GPU acceleration

---

## License

This project is released under the MIT License.
