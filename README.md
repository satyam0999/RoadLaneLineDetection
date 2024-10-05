
# Road Lane Detection Project

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

\`\`\`bash
pip install matplotlib numpy opencv-python moviepy Pillow
\`\`\`

### Cloning the Repository

Clone this repository using the following command:

\`\`\`bash
git clone <repository-url>
cd <repository-directory>
\`\`\`

Replace \`<repository-url>\` with the actual URL of your GitHub repository.

## Usage

### Processing a Video for Lane Detection

1. **Set Input and Output Paths:**
   Open the Python script and specify the path to the input video file and the desired output file.

   \`\`\`python
   white_output = 'path_to_output_file.mp4'
   clip1 = VideoFileClip("path_to_input_file.mp4")
   \`\`\`

2. **Run the Script:**
   Run the Python script to process the video:

   \`\`\`bash
   python lane_detection.py
   \`\`\`

   This will generate an output video with detected lane lines overlaid on the original frames.

### Launching the GUI

1. **Set Input Test Video and Result Video Paths:**
   In the GUI section of the code, make sure to set the correct paths for \`cap1\` and \`cap2\` to your input test video and the resulting lane-detected video, respectively:

   \`\`\`python
   cap1 = cv2.VideoCapture("path_to_input_test_video.mp4")
   cap2 = cv2.VideoCapture("path_to_resultant_lane_detected_video.mp4")
   \`\`\`

2. **Run the GUI:**
   Launch the GUI by running the script:

   \`\`\`bash
   python lane_detection_gui.py
   \`\`\`

   The GUI will show two windows: one displaying the original input video and the other showing the processed video with detected lanes.

## Code Explanation

### Lane Detection

1. **\`interested_region(img, vertices)\`**: This function isolates the region of interest (ROI) in the image, typically where the lanes are expected to be. It applies a mask to the image to retain only the region within the specified vertices.

2. **\`hough_lines(img, rho, theta, threshold, min_line_len, max_line_gap)\`**: This function performs the Hough Transform to detect lines in the image. It uses the OpenCV function \`HoughLinesP\` to detect probable lane lines.

3. **\`lines_drawn(img, lines, color=[255, 0, 0], thickness=6)\`**: This function averages the detected lines and draws them onto the image. It considers left and right lane lines separately and averages out their slopes to ensure smooth lane detection.

4. **\`process_image(image)\`**: This is the main function that processes each frame of the video. It converts the image to grayscale, applies masking, detects edges using Canny edge detection, identifies regions of interest, detects lines using Hough transforms, and finally overlays the detected lines on the original image.

### GUI for Displaying the Video

1. **\`show_vid()\` and \`show_vid2()\`**: These functions use OpenCV to read frames from the input test video and the resultant lane-detected video. The frames are displayed in the GUI using \`Tkinter\` and \`PIL.ImageTk\` for image rendering.

2. **Tkinter Setup**: The script uses \`Tkinter\` to create a simple GUI that shows two side-by-side windows: one displaying the original video and the other displaying the processed video with lane detection applied. The GUI also includes a quit button to exit the application.

## Project Flow

1. **Video Processing**: 
   - The input video is read frame by frame.
   - Each frame is processed to detect the lanes using edge detection and Hough transforms.
   - The detected lanes are drawn onto the frames, and the resulting video is saved.

2. **GUI Display**: 
   - After processing the video, the GUI displays both the original video and the processed video side by side.
   - The GUI continuously updates the frames in real-time to give the effect of video playback.

## Troubleshooting

1. **Error: \`MoviePy error: the file __path_to_input_file__ could not be found!\`**
   - Ensure you have specified the correct input and output file paths in the script.
   - Double-check the file extensions and ensure the file exists at the specified path.

2. **Error: \`cv2.error: (-215:Assertion failed) !ssize.empty() in function 'cv::resize'\`**
   - This error occurs if the video capture object (\`cap1\` or \`cap2\`) fails to open the video file. Ensure that the video paths are correct and that the videos are playable.

3. **Error: "No lane detected"**
   - This might occur if the lane lines are not clearly visible in the video. Make sure the video has clear lane markings, and adjust parameters like edge detection thresholds or the region of interest to improve detection.

4. **Issue: Camera Not Opening**
   - Ensure that the video file path is correct, and that you are using a compatible video format. If you are using a webcam for real-time input, ensure the correct webcam index is provided to \`cv2.VideoCapture()\`.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments
- This project makes use of the following open-source libraries: OpenCV, MoviePy, and Tkinter.
