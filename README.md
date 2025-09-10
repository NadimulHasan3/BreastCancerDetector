# Breast Cancer Prediction: Image Segmentation and Classification with Deep Learning
📋 ## Project Overview
This project develops a deep learning pipeline for breast cancer detection using ultrasound images. By integrating UNet-based segmentation with EfficientNetB3 classification, we significantly improve diagnostic accuracy from 42.01% to 86.39%. The system highlights tumor regions to assist classification and includes a web application for practical use.

🎯 ## Objectives
Implement UNet for accurate tumor segmentation in breast ultrasound images

Train EfficientNetB3 models to classify images as benign, malignant, or normal

Evaluate the impact of segmentation on classification performance

Develop a web application for practical clinical use

📊 ## Dataset
We used the Breast Ultrasound Images Dataset from Kaggle, which contains:

780 grayscale ultrasound images

Three classes: Benign (437), Malignant (210), Normal (133)

Expert-annotated ground truth segmentation masks

⚙️ ## Methodology
1. Data Preparation
Applied data augmentation (rotation, shear, flipping) to address class imbalance

Resized all images to 255×255 pixels

Used stratified sampling for train/validation/test splits

2. Baseline Classification
Implemented EfficientNetB3 with transfer learning (ImageNet weights)

Achieved 42.01% accuracy on raw images

3. Segmentation Enhancement
Trained UNet model for tumor segmentation

Achieved 95.55% segmentation accuracy

Overlaid segmented masks on original images to highlight tumor regions

4. Refined Classification
Retrained EfficientNetB3 on segmented images

Boosted classification accuracy to 86.39%

📈 ## Results
Baseline Model Performance (Raw Images)
Overall accuracy: 42.01%

Normal: 0.00 precision, 0.00 recall

Benign: 0.00 precision, 0.00 recall

Malignant: 0.42 precision, 1.00 recall

Refined Model Performance (Segmented Images)
Overall accuracy: 86.39%

Normal: 0.72 precision, 0.78 recall

Benign: 0.97 precision, 0.97 recall

Malignant: 0.83 precision, 0.79 recall

🚀 ## Implementation
The project includes a Flask-based web application that:

Allows users to upload ultrasound images

Classifies images into benign, malignant, or normal categories

Provides location-based recommendations for nearby clinics/hospitals
