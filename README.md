# 🦴 Fracture Detection and Segmentation Pipeline

This repository contains a complete deep learning pipeline for automatic fracture analysis in medical images. The system consists of **three models** that work in sequence to:

1. Detect the presence of a fracture.
2. Classify the severity of the fracture (simple or complex).
3. Segment the fractured area on the image.

---

## 📌 Pipeline Structure

### 1. Fracture Detection (Binary Classification)
- **Goal:** Predict whether there is a fracture in the X-ray image.
- **Dataset:** 17,000 labeled images.
- **Model:** CNN-based classifier (e.g., ResNet/EfficientNet).
- **Output:** `Fracture` / `No Fracture`.

### 2. Fracture Type Classification (Severity)
- **Goal:** Determine if the fracture is `Simple` or `Complex`.
- **Input:** Images where a fracture is detected by the first model.
- **Model:** Multi-class classification CNN.
- **Output:** `Simple Fracture` / `Complex Fracture`.

### 3. Fracture Segmentation
- **Goal:** Segment the exact area of the fracture.
- **Dataset:** 650 images with pixel-wise fracture masks.
- **Model:** `ResNet101` encoder with `Feature Pyramid Network (FPN)` decoder (pretrained).
- **Framework:** TensorFlow + [Segmentation Models](https://github.com/qubvel/segmentation_models).
- **Output:** Binary segmentation mask.

---

## 🛠️ Tech Stack

- **Frameworks:** TensorFlow / Keras
- **Backbones:** ResNet101, EfficientNet (optional)
- **Segmentation Architecture:** FPN
- **Augmentation:** Albumentations
- **Training Tools:** EarlyStopping, Learning Rate Scheduler, Image Generators

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/fracture-pipeline.git
   retrain the models
