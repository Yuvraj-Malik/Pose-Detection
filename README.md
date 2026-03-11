# 🏋️ AI Fitness Trainer: Real-Time Form Analysis

A computer vision-based fitness tracker that uses **TensorFlow MoveNet** and **OpenCV** to analyze exercise form in real-time. This project currently supports **Squats** and **High Knees**, providing live repetition counting, form scoring, and visual feedback via a webcam feed.

## 🚀 Features

* **Real-Time Pose Estimation:** Uses the lightning-fast MoveNet model to track 17 key body points.
* **Form Scoring:** Algorithms calculate joint angles to assign a score (0-100) for every repetition based on depth and posture.
* **Repetition Counting:** Automating counting logic based on state transitions (e.g., Up → Down → Up).
* **Visual Feedback:** Green/Red skeleton overlays indicate whether the user is in the correct position.
* **Bilingual Overlay:** Includes on-screen instructions in both **English** and **Hindi** (transliterated).

---

## 🛠️ Exercises Supported

### 1. Squats 🦵
Tracks the **Hip-Knee-Ankle** angle to determine squat depth.
* **Logic:**
    * **Down Phase:** Angle between 80°–130°.
    * **Up Phase:** Angle > 150°.
* **Scoring:**
    * 💯 **100 pts:** Perfect parallel depth (85°–115°).
    * 😐 **90 pts:** Good depth (80°–85° or 115°–130°).
    * ⚠️ **75 pts:** Acceptable (70°–80° or 130°–140°).
    * ❌ **50 pts:** Too shallow or too deep.

### 2. High Knees 🏃
Tracks knee elevation relative to hip height.
* **Logic:**
    * **Up Condition:** Knee coordinate is higher than Hip coordinate & Angle < 100°.
    * **Counting:** Increments by 0.5 per leg (Total = Left + Right).
* **Scoring:**
    * Based on how high the knee is raised and the sharpness of the leg angle during the peak of the movement.

---

## 💻 Tech Stack

* **Python 3.x**
* **OpenCV** (Computer Vision)
* **TensorFlow / TensorFlow Lite** (Pose Estimation Model)
* **NumPy** (Angle calculations)
* **Matplotlib** (Visualization)

---

## ⚙️ Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/Yuvraj-Malik/Pose-Detection
cd Pose-Detection
