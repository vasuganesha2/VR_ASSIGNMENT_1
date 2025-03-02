# Part 1: Coin Detection and Segmentation

## Overview
This project focuses on detecting and segmenting circular objects (coins) from an image using OpenCV. The steps include:

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
The script generates:
- **`detected_circles.png`**: The input image with detected coins highlighted.
- **`detected_circles_black_bg.png`**: Coins extracted with a black background.
- **`coin_1.png, coin_2.png, ...`**: Individual detected coin images.

## Requirements
- Python 3
- OpenCV (`cv2`)
- NumPy
- Matplotlib

## Usage
Run the script using:

```bash
python3 part1.py
