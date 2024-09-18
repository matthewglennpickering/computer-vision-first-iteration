
# Advanced Face Detection Program

## Overview

This project implements an advanced face detection system using only JavaScript and HTML without external libraries. The face detection is based on image processing techniques such as edge detection (using Sobel filters), region-based analysis, and simplified Haar-like feature detection. Dynamic skin color detection is also implemented to adapt to various lighting conditions and skin tones.

## Key Features

1. **Gaussian Blur for Smoothing**: Reduces image noise and enhances edge detection.
2. **Sobel Edge Detection**: Identifies edges in the image to help detect facial regions.
3. **Region-Based Detection**: Clusters edge-dense areas that may correspond to face-like shapes.
4. **Simplified Haar-like Feature Detection**: Detects geometric patterns that are face-like based on pixel intensity contrasts.
5. **Dynamic Skin Color Tuning**: Adjusts the skin color detection thresholds based on the detected face regions, improving the adaptability of the system under different lighting conditions.

## Program Components

### 1. Gaussian Blur

A 5x5 Gaussian kernel is applied to each frame from the video stream to smooth the image. This step helps to reduce noise in the image, making edge detection more reliable by softening hard transitions between pixel values.

```javascript
function applyGaussianBlur(imageData) {
    // 5x5 Gaussian kernel
    const kernel = [
        [1, 4, 7, 4, 1],
        [4, 16, 26, 16, 4],
        [7, 26, 41, 26, 7],
        [4, 16, 26, 16, 4],
        [1, 4, 7, 4, 1]
    ];
    const kernelWeight = 273; // Sum of kernel elements
    // Gaussian blur logic...
}
```

### 2. Sobel Edge Detection

This step involves applying two 3x3 Sobel kernels (one for detecting horizontal edges and one for vertical edges) to each frame. The magnitude of these gradients is computed to determine edge strength.

```javascript
const sobelX = [
    [-1, 0, 1],
    [-2, 0, 2],
    [-1, 0, 1]
];

const sobelY = [
    [-1, -2, -1],
    [0, 0, 0],
    [1, 2, 1]
];
```

### 3. Region-Based Detection

After edge detection, regions in the image where edge density is high are analyzed. These regions are clustered based on edge magnitude, and if the density exceeds a threshold, the region is marked as potentially face-like.

```javascript
function detectFaceRegions(edgeImageData) {
    // Region size and threshold for detecting edge-dense areas...
}
```

### 4. Simplified Haar-like Feature Detection

Haar-like feature detection compares pixel intensity in adjacent rectangular regions to identify face-like geometric structures. This simplified version calculates contrast between the left and right halves of each region, and detects features if the contrast difference exceeds a threshold.

```javascript
function detectHaarFeatures(edgeImageData) {
    // Feature detection based on pixel intensity contrast...
}
```

### 5. Dynamic Skin Color Detection

The skin color range is dynamically adjusted based on the average color of the detected face regions. This allows the system to adapt to different lighting conditions and skin tones.

```javascript
function adjustSkinColorRange(detectedRegions, imageData) {
    // Dynamic adjustment of skin color thresholds...
}
```

## Limitations

1. **Simplified Haar-like Features**: The simplified approach lacks the complexity and robustness of machine learning-based face detection techniques like those used in OpenCV or deep learning frameworks.
2. **Performance**: Since this program does not use optimized libraries, performance may degrade when processing large video streams or in real-time use cases.
3. **Environmental Sensitivity**: The system’s accuracy can be affected by variations in lighting, background, and skin tone. The dynamic color tuning helps mitigate this but does not fully solve the problem.

## Future Improvements

- Implement more advanced algorithms for feature detection, such as full Haar cascades or deep learning-based CNN models.
- Optimize the edge detection and region analysis algorithms for better real-time performance.
- Implement additional face features such as eyes, nose, and mouth detection.

## How to Use

1. Clone or download the HTML and JavaScript files from this repository.
2. Open the HTML file in a modern browser (e.g., Chrome or Firefox) to see the face detection in action.
3. Make sure you allow the webpage to access your webcam for the live video feed.

## References

- Sobel Edge Detection: [Wikipedia](https://en.wikipedia.org/wiki/Sobel_operator)
- Gaussian Blur: [Wikipedia](https://en.wikipedia.org/wiki/Gaussian_blur)
- Haar-like Feature Detection: [Wikipedia](https://en.wikipedia.org/wiki/Haar-like_feature)

## License

This project is licensed under the MIT License.
# computer-vision-first-iteration
