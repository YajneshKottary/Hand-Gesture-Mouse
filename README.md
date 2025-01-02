# Hand Gesture Mouse Control System

## Overview
This project implements an innovative hand gesture-based mouse control system using computer vision and machine learning. By leveraging MediaPipe's hand tracking capabilities and a custom-trained gesture recognition model, users can control their computer's mouse cursor through natural hand movements and gestures.

## Features
The system offers a comprehensive set of features for intuitive mouse control:

- Real-time hand tracking and gesture recognition
- Smooth cursor movement using index finger tracking
- Click actions triggered by specific hand gestures
- Visual feedback with hand landmark visualization
- Adjustable sensitivity and screen mapping
- Support for various screen resolutions

## Prerequisites
Before running the system, ensure you have the following dependencies installed:

## Installation
1. Clone the repository:

2. Install the required packages:
```bash
pip install -r requirements.txt
```

## Usage
To start the gesture mouse control system:

1. Run the main script:
```bash
python mouse_app.py
```

2. Position yourself in front of the camera:
   - Ensure good lighting conditions
   - Keep your hand within the camera's field of view
   - Maintain a distance of approximately 50cm from the camera

3. Use the following gestures:
   - Pointer gesture: Move cursor
   - OK gesture: Left click
   - Open hand: Release click
   - Close hand: No action

4. Press 'q' to exit the application

## Configuration
You can customize the system's behavior by modifying the following parameters in the `GestureMouseController` class:

```python
# Screen resolution
screen_width = 1920
screen_height = 1080

# Smoothing factor for cursor movement (0.0 to 1.0)
smooth_factor = 0.5

# Detection confidence thresholds
min_detection_confidence = 0.7
min_tracking_confidence = 0.5
```

## Technical Details

### Hand Tracking
The system uses MediaPipe Hands for accurate hand landmark detection, tracking 21 3D landmarks on each hand. These landmarks are processed to:
- Calculate relative positions for gesture recognition
- Track the index finger tip for cursor control
- Detect specific hand poses for mouse actions

### Gesture Recognition
The gesture recognition system employs two classifiers:
1. KeyPoint Classifier: Recognizes static hand poses
2. Point History Classifier: Tracks dynamic hand movements

### Mouse Control Implementation
Mouse control is achieved through:
- Coordinate mapping between camera space and screen space
- Smoothing algorithms for stable cursor movement
- Gesture-to-action mapping for click operations
- Debouncing logic to prevent accidental clicks

## Troubleshooting

Common issues and solutions:

1. Cursor Movement Issues:
   - Adjust the smooth_factor for more/less cursor stability
   - Ensure proper lighting conditions
   - Maintain appropriate distance from camera

2. Recognition Problems:
   - Recalibrate the system by adjusting confidence thresholds
   - Ensure hand is fully visible in camera frame
   - Check for background interference

3. Performance Issues:
   - Close resource-intensive background applications
   - Reduce camera resolution if needed
   - Update graphics drivers

## Contributing
Contributions are welcome! Please feel free to submit pull requests or open issues for:
- Bug fixes
- New features
- Documentation improvements
- Performance optimizations

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments
- MediaPipe team for their hand tracking implementation
- OpenCV community for computer vision tools
- Contributors to the mouse control package

## Contact
For questions, suggestions, or support, please:
- Open an issue in the GitHub repository
- Contact the maintainer at: maintainer@example.com

---
**Note**: This system is designed for research and educational purposes. Performance may vary based on hardware specifications and environmental conditions.
