# Alzheimer's Disease MRI Classification Using Deep Learning

## Overview

This project presents a comparative deep learning study for multiclass Alzheimer's disease classification using brain MRI scans. Three architectures were developed, trained, and evaluated on the same dataset to investigate how different model designs influence classification performance.

The study focuses on identifying four stages of Alzheimer's disease:

* Non-Demented
* Very Mild Demented
* Mild Demented
* Moderate Demented

Three deep learning approaches were implemented and compared:

1. ResNet18 + CBAM (Convolutional Block Attention Module)
2. Region-Aware ResNet + Transformer Attention
3. EfficientNet-B0 + Attention

The project was developed as part of the CSAI 486 - Special Topics in AI course at the American University of Ras Al Khaimah (AURAK).

---

## Problem Statement

Early diagnosis of Alzheimer's disease is critical for treatment planning and improving patient outcomes. Manual MRI interpretation can be challenging and time-consuming.

This project investigates whether modern deep learning architectures can accurately classify Alzheimer's disease stages from MRI scans and identifies the most effective approach under limited computational resources.

---

## Dataset

**Dataset:** Augmented Alzheimer MRI Dataset

Source:
https://www.kaggle.com/datasets/uraninjo/augmented-alzheimer-mri-dataset

### Classes

* Non-Demented
* Very Mild Demented
* Mild Demented
* Moderate Demented

### Dataset Split

| Dataset    | Percentage | Samples |
| ---------- | ---------- | ------- |
| Training   | 70%        | 2800    |
| Validation | 15%        | 600     |
| Testing    | 15%        | 600     |

---

## Preprocessing Pipeline

The following preprocessing steps were applied:

* Image resizing to 128×128 pixels
* Pixel normalization to [-1,1]
* Random horizontal flipping
* Random rotation (±10°)
* Stratified train-validation-test splitting

Additional preprocessing for Model 2:

* Region of Interest (ROI) extraction
* Brain-region masking

---

## Model Architectures

### 1. ResNet18 + CBAM

A pretrained ResNet18 backbone enhanced with Convolutional Block Attention Modules (CBAM).

Features:

* Transfer Learning
* Attention-based feature refinement
* Global Average Pooling
* Dropout Regularization

This model achieved the highest performance among all tested approaches.

---

### 2. Region-Aware ResNet + Transformer

A hybrid architecture combining CNN feature extraction with transformer attention.

Features:

* ROI-based preprocessing
* Channel attention
* Transformer encoder layers
* Global contextual feature modeling

The objective was to capture both local MRI features and long-range dependencies.

---

### 3. EfficientNet-B0 + Attention

A lightweight architecture designed for computational efficiency.

Features:

* EfficientNet-B0 backbone
* Attention module
* Label smoothing
* Reduced computational complexity

This model was designed for environments with limited hardware resources.

---

## Technologies Used

* Python
* PyTorch
* NumPy
* Scikit-Learn
* OpenCV
* Matplotlib
* Deep Learning
* Transfer Learning
* Computer Vision

---

## Experimental Results

### Performance Comparison

| Model                             | Accuracy | Weighted F1 |
| --------------------------------- | -------- | ----------- |
| ResNet18 + CBAM                   | 85.33%   | 0.85        |
| Region-Aware ResNet + Transformer | 78.00%   | 0.78        |
| EfficientNet-B0 + Attention       | 73.00%   | 0.72        |

---

## Key Findings

* ResNet18 + CBAM delivered the strongest overall performance.
* Lightweight attention significantly improved CNN feature extraction.
* Transformer-based architectures required more data and computational resources to outperform CNN-based methods.
* EfficientNet provided computational efficiency but lower classification accuracy.
* Increasing model complexity alone did not guarantee better results.

---

## Agentic AI Extension

The project extends beyond classification by integrating an agentic workflow capable of generating automated explanations and reports based on predicted Alzheimer's disease stages.

This demonstrates how AI systems can support medical decision-making workflows beyond prediction alone.

---

## Future Improvements

Potential enhancements include:

* Multimodal learning using clinical metadata
* Integration of demographic information
* Testing on external datasets such as ADNI and OASIS
* Longer training schedules
* Advanced augmentation strategies
* Explainable AI visualization methods
* Full deployment of the agentic reporting pipeline

---

## Skills Demonstrated

* Deep Learning
* Medical Image Analysis
* Computer Vision
* Transfer Learning
* Attention Mechanisms
* Transformer Architectures
* PyTorch Development
* Data Preprocessing
* Model Evaluation
* Research Methodology
* Comparative Experimental Design

---

## Team Members

* Fatema Alali
* Jannat Waqass
* Mennah Darwish
* Yasmien Abou Saeb

---

## Author Contribution

Contributed to model development, experimentation, evaluation, research analysis, and project documentation as part of a collaborative team project.

---

## License

This project is intended for academic and educational purposes.

