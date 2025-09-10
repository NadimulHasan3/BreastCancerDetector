# Breast Cancer Prediction: Image Segmentation and Classification with Deep Learning

## 📋 Project Overview
This project develops a deep learning pipeline for breast cancer detection using ultrasound images. By integrating **UNet-based segmentation** with **EfficientNetB3 classification**, the system significantly improves diagnostic accuracy from **42.01%** to **86.39%**. Tumor regions are highlighted to assist classification, and a **web application** is included for practical clinical use.

---

## 🎯 Objectives
- Implement **UNet** for accurate tumor segmentation in breast ultrasound images.
- Train **EfficientNetB3** models to classify images as **benign, malignant, or normal**.
- Evaluate the impact of segmentation on classification performance.
- Develop a **web application** for practical clinical use.

---

## 📊 Dataset
The project uses the [Breast Ultrasound Images Dataset (Kaggle)](https://www.kaggle.com/datasets/aryashah2k/breast-ultrasound-images-dataset), which contains:
- **780 grayscale ultrasound images**
- Three classes:
  - **Benign:** 437 images
  - **Malignant:** 210 images
  - **Normal:** 133 images
- Expert-annotated ground truth **segmentation masks**

---

## ⚙️ Methodology

### 1. Data Preparation
- Applied **data augmentation** (rotation, shear, flipping) to address class imbalance.
- Resized all images to **255×255 pixels**.
- Used **stratified sampling** for train/validation/test splits.

### 2. Baseline Classification
- Implemented **EfficientNetB3** with transfer learning (ImageNet weights).
- Achieved **42.01% accuracy** on raw images.

### 3. Segmentation Enhancement
- Trained **UNet** model for tumor segmentation.
- Achieved **95.55% segmentation accuracy**.
- Overlaid segmented masks on original images to highlight tumor regions.

### 4. Refined Classification
- Retrained **EfficientNetB3** on segmented images.
- Boosted classification accuracy to **86.39%**.

---

## 📈 Results

### Baseline Model Performance (Raw Images)
| Class     | Precision | Recall |
|-----------|-----------|--------|
| Normal    | 0.00      | 0.00   |
| Benign    | 0.00      | 0.00   |
| Malignant | 0.42      | 1.00   |
**Overall Accuracy:** 42.01%

### Refined Model Performance (Segmented Images)
| Class     | Precision | Recall |
|-----------|-----------|--------|
| Normal    | 0.72      | 0.78   |
| Benign    | 0.97      | 0.97   |
| Malignant | 0.83      | 0.79   |
**Overall Accuracy:** 86.39%

---

## 🚀 Implementation

The project includes a **Flask-based web application** that:
- Allows users to **upload ultrasound images**
- Classifies images into **benign, malignant, or normal** categories
- Provides **location-based recommendations** for nearby clinics/hospitals

---

## 🛠️ Installation

1. Clone this repository:
```bash
git clone https://github.com/yourusername/breast-cancer-prediction.git
cd breast-cancer-prediction
