# Gesture Recognition

The purpose of this script is to detect a specific gesture within a video sequence. It accomplishes this by comparing the gesture representation (an image or a short video clip) with each frame of the test video. If the gesture is detected in a frame, the script overlays the word "DETECTED" in bright green on the top right corner of the frame.

## Assumptions:
The gesture representation provided accurately represents the gesture to be detected.
The test video contains gestures that may not be exactly similar to the gesture representation but share similar characteristics.
The test video is in a common video format compatible with OpenCV (e.g., MP4, AVI).
The gesture occurs within the test video with varying scale, orientation, and background.

## Dependencies:
The script requires the OpenCV library (cv2) for image and video processing. Install it using the following command:
pip install opencv-python

## Output


https://github.com/sufyn/gesture_recognition/assets/97327266/184ccb87-99ed-4c24-97f8-f7b5a04a7849



## Approach:
Loading Gesture Representation: The script loads the gesture representation (image or video clip) using OpenCV.

Initializing Feature Detector: It initializes the Scale-Invariant Feature Transform (SIFT) detector, a robust feature detection algorithm.

Feature Extraction: The script detects keypoints and computes descriptors for the gesture representation using SIFT. This step captures distinctive features of the gesture.

Reading Test Video: It reads the test video sequence frame by frame using OpenCV's video capture functionality.

Feature Matching: For each frame of the test video, the script detects keypoints and computes descriptors. It then matches these descriptors with those of the gesture representation using the Brute-Force Matcher provided by OpenCV.

Filtering Matches: To ensure reliable matches, the script applies a ratio test to filter out low-quality matches and retain only high-quality matches.

Gesture Detection: If a sufficient number of good matches are found between the gesture representation and a frame of the test video, the script considers the gesture detected in that frame.

Overlaying Text: Upon detecting the gesture in a frame, the script overlays the text "DETECTED" in bright green on the top right corner of the frame using OpenCV's drawing functions.

Displaying Output: The processed frames with the overlaid text are displayed in a window using OpenCV.

Saving Output: Finally, the script writes the processed frames to an output video file.
