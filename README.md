# Part 1: Coin Detection and Segmentation

## Overview
This Jupyter Notebook focuses on detecting and segmenting circular objects (coins) from an image using OpenCV. The steps include:

- Preprocessing the image
- Detecting circular objects
- Masking and extracting individual coins

## Approach

### 1. Image Preprocessing
- Load the input image.
- Convert it to grayscale.
- Resize the image for consistent processing.
- Apply Gaussian and Median blurring to reduce noise.

### 2. Thresholding and Contour Detection
- Use adaptive thresholding to create a binary mask.
- Find external contours to identify potential coin-like objects.
- Filter contours based on area and circularity.

### 3. Coin Detection and Masking
- Fit circles around detected contours.
- Draw detected circles and contours for visualization.
- Create a mask to segment detected coins from the background.
- Save the masked image.

### 4. Segmentation of Individual Coins
- Extract each detected coin as a separate image.
- Save individual coin images for further processing.

## Outputs
The notebook generates:
- **`detected_circles.png`**: The input image with detected coins highlighted.
- **`detected_circles_black_bg.png`**: Coins extracted with a black background.
- **`coin_1.png, coin_2.png, ...`**: Individual detected coin images.

## Requirements
- Python 3
- Jupyter Notebook
- OpenCV (`cv2`)
- NumPy
- Matplotlib

## Usage
To run this project:
1. Open the Jupyter Notebook:
   ```bash
   jupyter notebook coin.ipynb


# Part 2: Feature Matching, Homography Estimation, and Panorama Stitching

This section continues the panorama stitching process by detecting keypoints, matching features, computing homography, and finally stitching the images together into a seamless panorama.

## Steps Involved:

### 1. **Feature Detection & Matching**
   - **SIFT (Scale-Invariant Feature Transform)** is used to detect keypoints and compute descriptors for both images.
   - To improve keypoint selection, we set a higher `contrastThreshold` to remove low-contrast keypoints.
   - **FLANN (Fast Library for Approximate Nearest Neighbors)** is employed for feature matching.
   - Lowe’s ratio test is applied to filter out poor matches, retaining only high-confidence feature correspondences.

### 2. **Homography Estimation**
   - The best transformation (homography) between the two images is computed using **RANSAC (Random Sample Consensus)**.
   - RANSAC helps eliminate outliers and ensures that only consistent matches are used to estimate the transformation matrix.
   - The resulting **Homography Matrix (H)** allows us to warp one image to align it with the other.

### 3. **Image Warping & Stitching**
   - Using the homography matrix, the first image is warped to align with the second image’s perspective.
   - We determine the size of the final panorama by computing the transformed corner positions.
   - A **translation adjustment** ensures that the warped image fits within the panorama dimensions.
   - The second image is then overlaid at its correct position within the panorama.

### 4. **Saving & Displaying Results**
   - The final stitched panorama is saved as **`panorama_result.png`**.
   - The output is also displayed using Matplotlib for visualization.

### **Final Output**
After running this section, the generated panoramic image will seamlessly blend the input images into a wider field of view.


# Part 2: Feature Matching, Homography Estimation, and Panorama Stitching

## Overview
This section continues the panorama stitching process by detecting keypoints, matching features, computing homography, and finally stitching the images together into a seamless panorama.

## Steps Involved:

### 1. **Feature Detection & Matching**
   - **SIFT (Scale-Invariant Feature Transform)** is used to detect keypoints and compute descriptors for both images.
   - To improve keypoint selection, we set a higher `contrastThreshold` to remove low-contrast keypoints.
   - **FLANN (Fast Library for Approximate Nearest Neighbors)** is employed for feature matching.
   - Lowe’s ratio test is applied to filter out poor matches, retaining only high-confidence feature correspondences.

### 2. **Homography Estimation**
   - The best transformation (homography) between the two images is computed using **RANSAC (Random Sample Consensus)**.
   - RANSAC helps eliminate outliers and ensures that only consistent matches are used to estimate the transformation matrix.
   - The resulting **Homography Matrix (H)** allows us to warp one image to align it with the other.

### 3. **Image Warping & Stitching**
   - Using the homography matrix, the first image is warped to align with the second image’s perspective.
   - We determine the size of the final panorama by computing the transformed corner positions.
   - A **translation adjustment** ensures that the warped image fits within the panorama dimensions.
   - The second image is then overlaid at its correct position within the panorama.

### 4. **Saving & Displaying Results**
   - The final stitched panorama is saved as **`panorama_result.png`**.
   - The output is also displayed using Matplotlib for visualization.

## Final Output
After running this section, the generated panoramic image will seamlessly blend the input images into a wider field of view.

---

# Requirements
Ensure you have Python 3 and the following dependencies installed:

```bash
   pip install opencv-python numpy matplotlib
```


## Usage
To run this project:
1. Open the Jupyter Notebook:
   ```bash
   jupyter notebook coin.ipynb


