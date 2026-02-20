# 😊 Real-Time Emotion Detection System

> A real-time facial emotion recognition system built with Python, OpenCV, and a custom-trained Keras deep learning model — no DeepFace or cloud APIs required.

---

## 🎯 Overview

This project uses your **webcam feed** to detect faces in real time and classify the emotion displayed on each face into one of **7 categories** — all running locally on your machine.

It combines:
- **OpenCV's Haar Cascade** for fast face detection
- A **pre-trained CNN model** (`.hdf5`) for emotion classification
- Live bounding boxes and emotion labels rendered on the video stream

---

## 🧠 Detected Emotions

| Label | Emoji |
|-----------|-------|
| Angry | 😠 |
| Disgust | 🤢 |
| Fear | 😨 |
| Happy | 😄 |
| Sad | 😢 |
| Surprise | 😲 |
| Neutral | 😐 |

---

## 🗂️ Project Structure

```
📦 emotion-detection/
 ┣ 📜 emotion_detection.py               ← Main script
 ┣ 📦 emotion_model.hdf5                 ← Pre-trained Keras CNN model
 ┣ 📄 haarcascade_frontalface_default.xml ← OpenCV face detector
 ┗ 📜 README.md                          ← This file
```

---

## ⚙️ How It Works

1. **Webcam capture** — OpenCV reads frames from your default camera
2. **Face detection** — Haar Cascade scans each frame for faces
3. **Preprocessing** — Detected face ROI is converted to grayscale, resized to `64×64`, and normalized (`/ 255.0`)
4. **Prediction** — The CNN model outputs a probability distribution across 7 emotion classes
5. **Display** — A green bounding box and the predicted emotion label are drawn on the live frame

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.x | Core language |
| OpenCV (`cv2`) | Webcam capture & face detection |
| Keras / TensorFlow | Loading & running the CNN model |
| NumPy | Array manipulation & preprocessing |

---

## 📦 Installation

### 1. Clone the repository
```bash
git clone https://github.com/your-username/emotion-detection.git
cd emotion-detection
```

### 2. Install dependencies
```bash
pip install opencv-python numpy tensorflow keras
```

> **macOS users:** The script uses `cv2.CAP_AVFOUNDATION` for webcam compatibility — no extra setup needed.

---

## ▶️ Usage

```bash
python emotion_detection.py
```

- A live webcam window titled **"Emotion Detection System"** will open
- Detected faces are highlighted with a **green rectangle**
- The predicted emotion label appears **above each face**
- Press **`q`** to quit

---

## 📋 Requirements

```
opencv-python
numpy
tensorflow
keras
```

> You can generate a `requirements.txt` with:
> ```bash
> pip freeze > requirements.txt
> ```

---

## 🔧 Configuration

| Parameter | Value | Description |
|---|---|---|
| Input size | `64 × 64` | Grayscale face ROI fed to the model |
| Detection scale | `1.3` | Haar Cascade scale factor |
| Min neighbors | `5` | Haar Cascade min neighbors |
| Camera index | `0` | Default webcam |

---

## 📌 Notes

- Make sure `emotion_model.hdf5` and `haarcascade_frontalface_default.xml` are in the **same directory** as the script
- Requires a working webcam
- Works best with **good lighting** and a **front-facing camera angle**
- Tested on **macOS** (`CAP_AVFOUNDATION`); for Windows/Linux, remove the second argument from `cv2.VideoCapture(0)`

---

## 🚀 Future Improvements

- [ ] Add confidence percentage display alongside emotion label
- [ ] Support for multiple simultaneous face tracking
- [ ] Save detected emotion logs to CSV
- [ ] Build a GUI dashboard with emotion frequency graphs
- [ ] Add support for video file input (not just webcam)

---

## 📬 Contact

- 🐙 **GitHub:** [your-username](https://github.com/DeveloperSomnath)
- 📧 **Email:** `somnath7216das@email.com`
