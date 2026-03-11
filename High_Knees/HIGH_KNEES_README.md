# High Knees Detection and Scoring

This project uses TensorFlow MoveNet (TFLite) and OpenCV to detect high knees from a webcam feed in real time.
It estimates body keypoints, computes knee angles, counts reps, and assigns a score based on movement quality.

## Project Files

- `High_Knees.ipynb`: Main notebook with the full pipeline.
- `3.tflite`: MoveNet model file used by the notebook.
- `Requirements.txt`: Python dependencies.

## How It Works

1. Pose detection
- MoveNet extracts 17 body keypoints from each webcam frame.

2. Angle calculation
- The notebook computes hip-knee-ankle angles for both legs.
- A short smoothing buffer is used to reduce noise.

3. Rep detection
- Each leg is tracked independently with up/down state transitions.
- Total rep count increases by 0.5 per leg transition.

4. Scoring
- Knee close to hip and knee angle < 90 gives 100 points.
- Slightly lower knee or angle < 120 gives 80 points.
- Otherwise, score is 60 points.

5. Visual feedback
- Skeleton color indicates form quality.
- Live rep counter and latest score are shown on the video frame.

## Setup

1. Install Python 3.8 or newer.
2. Open a terminal in this folder.
3. Install dependencies:

```bash
pip install -r Requirements.txt
```

## Run

1. Open `High_Knees.ipynb` in Jupyter (VS Code notebook works well).
2. Run cells from top to bottom.
3. When the main loop cell starts, webcam detection begins.
4. Press `q` in the video window to stop.

## Notes

- Use a well-lit area and keep your full body visible.
- Ensure `3.tflite` is in the same folder as the notebook.
- You can tune thresholds in the notebook for your camera angle and range of motion.

## Tech Stack

Python, TensorFlow Lite, OpenCV, NumPy
