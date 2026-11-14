#  Real-Time Object Detection & Traffic Violation Analysis

[![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-Computer_Vision-5C3EE8?logo=opencv&logoColor=white)](https://opencv.org/)
[![NumPy](https://img.shields.io/badge/NumPy-Numerical_Computing-013243?logo=numpy&logoColor=white)](https://numpy.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

A computer vision system that detects pedestrians and vehicles in real time from video footage and analyzes their compliance with traffic rules.
The system recognizes objects in the video stream, tracks their positions, and flags violations by checking for overlaps with predefined zones.

##  Table of Contents

- [Purpose](#-purpose)
- [Tech Stack](#-tech-stack)
- [Algorithm Flow](#-algorithm-flow)
- [Defined Zones](#-defined-zones)
- [Results](#-results)
- [Getting Started](#-getting-started)

##  Purpose

- Detect pedestrians and vehicles in critical areas such as intersections and crosswalks
- Automatically identify movements that violate traffic rules
- Visually flag violations for the user

##  Tech Stack

| Technology | Purpose |
|---|---|
| **Python 3** | Core language |
| **OpenCV** | Image processing |
| **NumPy** | Numerical computation |
| `cv2.createBackgroundSubtractorMOG2()` | Background subtraction |
| `cv2.findContours()` | Contour analysis |
| `cv2.pointPolygonTest()` | Zone overlap detection |

##  Algorithm Flow

1. Video source is loaded.
2. For each frame:
   - Convert to grayscale and apply Gaussian blur
   - Perform background subtraction (MOG2)
   - Clean up the image using thresholding and morphological operations
   - Detect objects through contour analysis
   - Classify each object as a pedestrian or vehicle based on aspect ratio
   - Analyze violations against predefined zones (intersection / crosswalk)
   - Draw a color-coded bounding box around each object based on its class
   - Add a violation label on the frame when applicable

##  Defined Zones

- **Intersection Zone:** An area pedestrians should not cross.
- **Crosswalk Zone:** An area vehicles should not violate.

##  Results

- Pedestrians and vehicles are detected with high accuracy.
- Violations within defined zones are successfully identified.
- The real-time visual alert mechanism works as intended.

##  Getting Started

1. Install the required libraries:

```bash
pip install opencv-python numpy
```

2. Run the script:

```bash
python main.py
```

> **Note:** Make sure `Train.mp4` and `Test.mp4` are present in the project directory before running.
