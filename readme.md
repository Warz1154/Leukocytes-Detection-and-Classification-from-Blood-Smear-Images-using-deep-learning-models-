# Leukocyte Detection and Classification from Blood Smear Images

## Overview
This repository focuses on automating hematological diagnostics by leveraging **deep learning** to detect and classify leukocytes (white blood cells) from blood smear images. It includes datasets, preprocessing pipelines, and model implementations evaluated for efficiency and accuracy.

The project aligns with the objectives of the **CytologIA Data Challenge**, an international competition aimed at transforming hematological diagnostics with AI.

---

## Table of Contents
1. [Introduction](#introduction)
2. [Data Exploration and Preprocessing](#data-exploration-and-preprocessing)
3. [Models and Results](#models-and-results)
4. [Evaluation Metrics](#evaluation-metrics)
5. [Usage](#usage)
6. [Contributing](#contributing)

---

## Introduction
Hematology, the study of blood diseases, has traditionally relied on manual examination of blood smears under a microscope. This process is:
- Time-consuming
- Requires significant expertise
- Prone to diagnostic disparities

Using **deep learning models**, this project detects leukocytes with bounding boxes and classifies them into **23 distinct classes**, streamlining the diagnostic process.

---

## Data Exploration and Preprocessing

### Dataset
- **Size:** 52,748 images, 69,168 rows (bounding box data)
- **Classes:** 23
- **Format:** COCO and YOLO annotation formats

### Preprocessing Steps
1. Removed overlapping bounding boxes (same and different classes).
2. Downsampled classes to balance the dataset (600 samples per class).
3. Adjusted bounding boxes out of range.
4. Resized images for consistent input dimensions.

---

## Models and Results

### Models Implemented
1. **YOLOv5**:
   - Precision: 0.756
   - Recall: 0.84
   - mAP50: 0.824

2. **YOLOv8**:
   - Enhanced multi-scale feature fusion
   - Lightweight and efficient architecture

3. **Faster R-CNN**:
   - mAP: 0.7348
   - Average IoU: 0.8564

4. **UNET + MEDSAM**:
   - Test F1 Score: 0.9158
   - Test mIoU: 0.8030

5. **RetinaNet**:
   - Accuracy: 0.4533
   - F1 Score: 0.4310

### Results Summary
- YOLOv8 demonstrated the best real-time detection efficiency.
- UNET + MEDSAM achieved high segmentation performance.

---

## Evaluation Metrics
- **Precision**: Proportion of correct predictions among all predictions.
- **Recall**: Proportion of correctly detected objects among all ground truth objects.
- **F1-Score**: Balances precision and recall.
- **Mean Average Precision (mAP)**: Assesses detection performance across all classes.
- **Intersection over Union (IoU)**: Measures overlap between predicted and ground truth bounding boxes.

---

## Usage

### Prerequisites
- Python 3.8+
- PyTorch
- YOLOv5 and YOLOv8 frameworks

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/leukocyte-detection.git
   cd leukocyte-detection
