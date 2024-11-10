
# Real-Time Pose and Gesture Detection Using Mediapipe

## Project Description

This project leverages Python, OpenCV, and Mediapipe to create a comprehensive system for real-time detection and tracking of human body poses, facial landmarks, and hand gestures. The application processes live video feed from a webcam, detects key landmarks using Mediapipe's holistic model, and visualizes the landmarks on the output feed. Additionally, keypoints extracted from these detections can be stored as numpy arrays, enabling further analysis and use in machine learning models.

## Features

- **Real-Time Landmark Detection**: 
  - Captures live video feed and detects facial, pose, and hand landmarks in real-time.
  
- **Custom Visualization**: 
  - Uses Mediapipe's drawing utilities to render detected landmarks with customizable drawing specifications.
  
- **Keypoint Extraction**: 
  - Extracts and stores keypoints as numpy arrays for subsequent data analysis or training purposes.
  
- **Data Collection Framework**: 
  - Organizes captured data in a structured format to facilitate machine learning projects.

## Installation

Ensure Python is installed, and then install the required packages:

```bash
pip install --upgrade pip
pip install opencv-python numpy mediapipe matplotlib
```

## How to Run the Project

1. **Clone the Repository**:
2. **Run the Script**:

```bash
python main.py
```

Press `q` to stop the video feed and close the window.

## Code Breakdown

### Core Functions

- **mediapipe_detection(image, model)**:
  - Preprocesses the input image, makes predictions using the Mediapipe model, and returns the image and results.

- **draw_landmarks(image, results)**:
  - Draws facial, pose, and hand landmarks on the image using custom drawing specifications.

- **extract_keypoints(results)**:
  - Extracts keypoints from the detected landmarks and concatenates them into a numpy array.

### Real-Time Video Processing

The main loop captures frames from the webcam, processes them with Mediapipe, and visualizes the detection results.

### Data Collection

The project includes a loop structure to capture video sequences for different actions:

```python
for action in actions:
    for sequence in range(no_sequences):
        os.makedirs(os.path.join(DATA_PATH, action, str(sequence)), exist_ok=True)
```

### Directory Structure

The data collected is stored in a structured format for easy access:

```
H_Data/
    hello/
        0/
        1/
        ...
    thanks/
        0/
        1/
        ...
    iloveyou/
        0/
        1/
        ...
```

## Future Enhancements

- Integration of gesture recognition models for specific actions.
- Improved user interface for better interaction.
- Enhanced data augmentation techniques for better model training.
