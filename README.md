# People Flow Detection Using Object Tracking & Heatmap Visualization

## 1. Project Overview

This project implements a computer vision-based people flow detection system using YOLO11s and ByteTrack. It detects and tracks people across video frames, counts people entering and exiting a defined area using two horizontal counting lines, and generates a movement heatmap to visualize pedestrian presence intensity.

## 2. Objectives

- Detect people using a pre-trained YOLO11s model.
- Track individuals using ByteTrack.
- Assign unique tracking IDs to detected people.
- Count IN and OUT movements using line-crossing logic.
- Generate a pedestrian movement heatmap.
- Produce an annotated output video with live counters.

## 3. Technologies Used

- Python
- YOLO11s
- Ultralytics
- ByteTrack
- OpenCV
- NumPy
- Matplotlib
- Google Colab
- NVIDIA Tesla T4 GPU

## 4. Dataset

Input Video: people-walking.mp4

Video Resolution: 1920 × 1080  
Frame Rate: 25 FPS  
Total Frames: 341  
Duration: 13.64 seconds

## 5. Detection and Tracking Methodology

YOLO11s detects people in each video frame using the COCO person class (class ID 0).

ByteTrack maintains object identities across consecutive frames and assigns unique tracking IDs.

## 6. IN/OUT Counting Logic

- IN: A person is counted when moving from above the upper horizontal line to below it.
- OUT: A person is counted when moving from below the lower horizontal line to above it.

Each tracking ID is counted only once.

## 7. Heatmap Generation

The centers of tracked bounding boxes are accumulated across video frames. Gaussian smoothing and color mapping are applied to visualize pedestrian movement intensity.

## 8. Output Files

- people_flow_output.mp4
- people_heatmap.png
- people_heatmap_overlay.png

## 9. Execution

The project is implemented in Google Colab.

Open the notebook and execute the cells sequentially to reproduce the detection, tracking, counting, and heatmap generation pipeline.

## 10. Conclusion

The project demonstrates how object detection and multi-object tracking can be integrated to perform pedestrian flow analysis and visualize movement intensity using computer vision.
