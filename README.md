# HistoSight AI — Breast Cancer Histopathology Classification

A thesis project comparing two approaches for classifying breast cancer histopathology images:
a supervised CNN baseline and a zero-shot CLIP classifier.

**Roskilde University (RUC) | Specialization Project | 2026**

---

## Project Overview

This project classifies 256×256 histopathology image tiles into two categories:
- **Cancer** — tiles containing tumor (class 1), angioinvasion (class 19), or DCIS (class 20)
- **Non-Cancer** — all other tissue types

---

## Models

### 1. Base CNN
- Input: 128×128 RGB histopathology tiles
- Architecture: Conv2D → BatchNorm → MaxPooling (×3) → GlobalAveragePooling → Dense → Sigmoid
- Optimizer: Nadam (lr=1e-5)
- Loss: Binary Crossentropy
- Trained for 30 epochs

### 2. Zero-Shot CLIP (ViT-B-16)
- Model: `ViT-B-16` pretrained on `laion2b_s34b_b88k`
- No training required
- Classification via image-text cosine similarity + softmax
- Prompt averaging for both cancer and non-cancer classes

---

## Dataset

**BRACS / Breast Cancer Histopathology Dataset**
- RGB color-normalized tiles: `rgbs_colorNormalizedWithTiles/tiles_256`
- Mask tiles: `masksWithTiles/tiles_256`
- Labels generated from mask pixel values

---

## Repository Structure

histosight-AI/

└── notebooks/

└── breast-cancer-detection-cnn-clipzs.ipynb

---

## Requirements

tensorflow
torch
open_clip_torch
scikit-learn
Pillow
matplotlib
numpy

---

## Group Members

- Zahidul Islam
- Kazi Nibras Dastagir Fariha
- Deepesh Raj Ghimire
- Rumana Afrin Rumi

**Supervisor:** Associate Professor Hemant Ghyavat
