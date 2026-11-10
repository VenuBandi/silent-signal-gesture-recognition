<div align="center">

# Silent Signal — Gesture Recognition

Real-time emergency gesture recognition using MediaPipe keypoints and a Motion BiLSTM.

[![GitHub stars](https://img.shields.io/github/stars/VenuBandi/silent-signal-gesture-recognition?style=for-the-badge&color=yellow)](https://github.com/VenuBandi/silent-signal-gesture-recognition/stargazers)

[![PyTorch](https://img.shields.io/badge/PyTorch-2.x-EE4C2C?logo=pytorch&logoColor=white)](https://pytorch.org)
[![MediaPipe](https://img.shields.io/badge/MediaPipe-Keypoints-blue)](https://mediapipe.dev)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

</div>

<br>

> This is the original college version of the project. The maintained repo with updated results and clean code is [silent-signal](https://github.com/VenuBandi/silent-signal).

---

## What It Does

Converts silent physical gestures into real-time emergency alerts — without transmitting audio, without reading lips, and without any visible interface for the person signaling.

```
Video Input → MediaPipe Landmarks → Motion Deltas → Motion BiLSTM → Gesture Class + Confidence
```

---

## Results

| Metric | Result |
|:--|:--:|
| Best Validation Accuracy | **76.85%** |
| Test Accuracy | **67.59%** |
| Inference Time | **0.39 ms** |
| Estimated FPS | **2,563** |

---

## Gesture Classes (9)

| Gesture | F1 |
|:--|:--:|
| Danger | **0.91** |
| Help | **0.88** |
| Abort | **0.84** |
| Need Backup | **0.80** |
| Watched | 0.74 |
| Proceed | 0.68 |
| Safe | 0.60 |
| Stay | 0.55 |
| No Gesture | 0.48 |

---

## Architecture

Face mesh + hand landmarks + upper-body pose keypoints → 30-frame sequence → Motion BiLSTM → gesture class.

A rule-based safety layer wraps the model: sustained eye closure (~2s) triggers or confirms the Safe state independent of prediction.

---

## Quick Start

```bash
git clone https://github.com/VenuBandi/silent-signal-gesture-recognition
cd silent-signal-gesture-recognition
pip install -r requirements.txt
python src/train_bilstm.py
python src/dashboard_app.py
```

---

## Stack

`Python` `PyTorch` `MediaPipe` `OpenCV` `Flask` `NumPy` `scikit-learn`

---

<div align="center">

If this project was useful, a ⭐ helps others find it.

</div>
