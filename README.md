# LumoraQ

Quantum Machine Learning for Satellite Image Analysis

---

## 1. Project Overview

LumoraQ investigates hybrid quantum-classical machine learning methods for satellite image classification using the EuroSAT dataset.

The project follows a structured progression:

1. Build a classical CNN baseline
2. Improve performance using architectural upgrades (StrongCNN)
3. Analyze results using metrics, graphs, and confusion matrix
4. Implement a Variational Quantum Classifier (VQC)
5. Develop a hybrid CNN + quantum pipeline

The goal is to evaluate quantum machine learning realistically against strong classical baselines.

---

## 2. Dataset

- EuroSAT dataset
- 27,000 satellite images
- 10 land-use classes:
  - AnnualCrop
  - Forest
  - HerbaceousVegetation
  - Highway
  - Industrial
  - Pasture
  - PermanentCrop
  - Residential
  - River
  - SeaLake

Preprocessing:
- Image size: 64×64
- Normalization applied
- Data augmentation used during training

---

## 3. Classical Model Development

### 3.1 Initial CNN

- 2 convolution layers
- MaxPooling layers
- Fully connected classifier
- CrossEntropyLoss
- Adam optimizer

Performance:
- Accuracy: 67%

---

### 3.2 Extended CNN Training

- Same architecture trained longer

Performance:
- Accuracy: 80.28%
- Loss: 0.0791

---

### 3.3 StrongCNN (Final Classical Model)

Architecture:
- Conv2D (3 → 32)
- BatchNorm + ReLU
- Conv2D (32 → 32)
- BatchNorm + ReLU
- MaxPooling
- Conv2D (32 → 64)
- BatchNorm + ReLU
- Conv2D (64 → 64)
- BatchNorm + ReLU
- MaxPooling
- Linear (16384 → 256)
- Dropout (0.4)
- Linear (256 → 10)

Performance:
- Accuracy: 88.83%
- Precision: 89%
- Recall: 89%
- F1 Score: 89%

Test set size: 5400 images

---

## 4. Training Graphs

Generated plots:
- Training vs Validation Accuracy
- Training vs Validation Loss

Key observations:
- Smooth convergence across epochs
- No major overfitting due to dropout and augmentation
- Validation closely tracks training performance
- Stable learning behavior after StrongCNN upgrade

---

## 5. Confusion Matrix Analysis

The confusion matrix shows strong diagonal dominance, meaning most predictions lie on the correct class axis.

### 5.1 Strong Diagonal Classes

High-performing classes:
- Forest (near-perfect classification)
- SeaLake (best overall performance)
- Residential
- Industrial

These classes show strong feature separability.

---

### 5.2 Misclassification Patterns

Most errors occur between vegetation-related classes:

- AnnualCrop
- HerbaceousVegetation
- PermanentCrop
- Pasture

---

### 5.3 Key Insight

- Strong diagonal dominance indicates strong classification performance
- Errors are structured, not random
- Model performs best on visually distinct land types
- Struggles with spectrally similar vegetation classes

---

## 6. Quantum Machine Learning (VQC)

A Variational Quantum Classifier was implemented using PennyLane.

---

### 6.1 Quantum Circuit Design

- 2-qubit system
- RX and RY encoding gates
- Pauli-Z expectation measurements
- Trainable parameters (weights)
- Gradient descent optimization

Example:

Input: [0.5, 0.2]  
Output: [0.8775, 0.9800]

---

### 6.2 VQC Training

Optimizer:
- Gradient Descent (PennyLane)

Training:
- 100 optimization steps

---

### 6.3 Loss Progression

- Initial loss: ~1.6395
- Step 20: 0.030337
- Step 40: 0.018537
- Step 60: 0.016034
- Step 80: 0.015287
- Step 100: 0.015035

---

### 6.4 Observations

- Loss decreases smoothly and consistently
- Quantum circuit is fully differentiable
- Gradient-based optimization works correctly
- Parameters converge to stable minimum
- Model successfully learns toy function behavior
- Not yet applied to real satellite dataset

---

## 7. Current Status

### Classical
- StrongCNN achieved 88.83% accuracy
- Full evaluation complete

### Quantum
- VQC successfully implemented
- Training verified with convergence
- Still operating on synthetic inputs

---

## 8. Research Direction

The next stage is a hybrid architecture:

CNN feature extractor  
→ dimensionality reduction (PCA)  
→ quantum variational circuit  
→ final classification

Goal:
Evaluate whether quantum layers provide measurable improvement over a strong classical baseline.

---

## 9. Next Steps

- Extract CNN feature embeddings
- Apply PCA or dimensionality reduction
- Feed features into quantum circuit
- Build hybrid CNN + VQC model
- Compare against 88.83% StrongCNN baseline
