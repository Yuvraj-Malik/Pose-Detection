# Squat Detection and Scoring

This project uses TensorFlow MoveNet (TFLite) and OpenCV to detect squats from a webcam feed in real time.
It estimates body keypoints, computes knee angles, counts repetitions, and scores form quality.

## Project Files

- `Squats.ipynb`: Main notebook with full squat logic.
- `3.tflite`: MoveNet model file used by the notebook.
- `Requirements.txt`: Python dependencies.

## How It Works

1. Pose detection
- MoveNet extracts 17 body keypoints from each frame.

2. Angle calculation
- Knee angles are computed from hip-knee-ankle points.

3. Rep detection
- A rep is detected when movement transitions from squat-down to standing-up.

4. Scoring
- Depth around 85 to 115 degrees gives 100 points.
- Near-good depth gives 90 points.
- Acceptable but less ideal depth gives 75 points.
- Too shallow or too deep gives 50 points.

5. Visual feedback
- Skeleton color reflects form state.
- Live rep count and latest score are overlaid on the video frame.

## Setup

1. Install Python 3.8 or newer.
2. Open a terminal in this folder.
3. Install dependencies:

```bash
pip install -r Requirements.txt
```

## Run

1. Open `Squats.ipynb` in Jupyter (VS Code notebook works well).
2. Run cells from top to bottom.
3. Start the main loop cell to begin webcam detection.
4. Press `q` in the video window to stop.

## Notes

- Use a well-lit area and keep your full body in frame.
- Ensure `3.tflite` is in the same folder as the notebook.
- Tune angle thresholds in the notebook if needed for your setup.

## Tech Stack

Python, TensorFlow Lite, OpenCV, NumPy
