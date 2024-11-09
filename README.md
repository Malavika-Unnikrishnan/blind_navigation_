# Object Detection with Position-Based Voice Commands

This project demonstrates a simple real-time object detection system using YOLOv8, OpenCV, and pyttsx3 for text-to-speech feedback. The application captures frames from the webcam, detects objects, and provides vocal commands to the user based on the detected object's position on the screen (left, center, or right). This functionality could be useful for assistive technology applications, guiding users with spoken instructions based on object positioning.

## Requirements

- Python 3.x
- [YOLOv8](https://github.com/ultralytics/ultralytics) (Ultralytics YOLO)
- [OpenCV](https://opencv.org/) (`opencv-python`)
- [pyttsx3](https://pyttsx3.readthedocs.io/) (text-to-speech)

You can install the required libraries using the following commands:

```bash
pip install ultralytics opencv-python pyttsx3
```

## How It Works

1. **Initialize YOLO Model**: Loads the YOLOv8 model for object detection.
2. **Setup Webcam**: Captures video frames from the webcam.
3. **Object Detection**: Detects objects in each frame and calculates the object’s position (left, center, or right).
4. **Voice Command Feedback**: Provides spoken feedback with commands to guide the user, based on the detected object's position.

### Regions for Position-Based Commands

- **Left**: Instructs the user to move right.
- **Right**: Instructs the user to move left.
- **Center**: Instructs the user to stop and assess.

## Code Structure

- `get_position_and_command()`: Determines the position of the object and generates a command based on the x-coordinate of the bounding box.
- `speak_command()`: Converts the generated command to speech using `pyttsx3` in a separate thread.
- Main loop: Processes each video frame, detects objects, annotates the frame, and displays the video feed with bounding boxes and commands.

## Usage

Run the script with:
```bash
python your_script_name.py
```

- **Exit**: Press `q` to stop the program.

## Example Output

In the video feed:
- Objects are marked with bounding boxes, showing the detected object's name, position, and command.
- The application gives voice feedback based on object positions, such as "Object detected Left. Move right."

## Troubleshooting

1. **Model Path**: Ensure `yolov8n.pt` is available in your working directory or specify the correct model path.
2. **Webcam Access**: Check if your webcam is properly connected and accessible.
3. **Text-to-Speech**: Ensure `pyttsx3` is installed and configured correctly for your system's TTS engine.



