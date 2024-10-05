# RoadLaneLineDetection

This project implements a lane detection system using Python, OpenCV, and MoviePy. The goal is to process a video input, detect lane lines, and display the results with an intuitive graphical interface (GUI) using Tkinter. The system processes images frame-by-frame, detects the lanes using Hough transforms, and outputs the processed video showing the detected lanes.

## Table of Contents
1. [Installation](#installation)
2. [Usage](#usage)
3. [Code Explanation](#code-explanation)
   - [Lane Detection](#lane-detection)
   - [GUI for Displaying the Video](#gui-for-displaying-the-video)
4. [Project Flow](#project-flow)
5. [Troubleshooting](#troubleshooting)
6. [License](#license)
7. [Acknowledgments](#acknowledgments)

## Installation

### Prerequisites

Ensure you have Python 3.x installed on your system. You will also need to install the following dependencies:

- `matplotlib`
- `numpy`
- `opencv-python`
- `moviepy`
- `Pillow`

You can install these dependencies using pip:

```bash
pip install matplotlib numpy opencv-python moviepy Pillow
