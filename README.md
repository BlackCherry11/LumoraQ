# LumoraQ

Quantum Machine Learning for Satellite Image Analysis

---

## 🎯 Goal

This project investigates hybrid quantum-classical machine learning methods for Earth observation data using the EuroSAT dataset.

The current stage focuses on building a strong classical baseline before introducing quantum models.

---

#Dataset

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

Images are resized to 64×64 and normalized before training.

---

#Model Architecture

A Convolutional Neural Network (CNN) was used:

- Conv2D (3 → 16 filters)
- ReLU
- MaxPooling
- Conv2D (16 → 32 filters)
- ReLU
- MaxPooling
- Fully Connected Layer (8192 → 128)
- Fully Connected Layer (128 → 10)
- CrossEntropy Loss
- Adam Optimizer

---

# Training Results

### Baseline (Initial Training)
- 1 epoch accuracy: **67%**
- Loss: **1.2602**

### Final Model (15 Epochs)
- Accuracy: **80.28%**
- Final training loss: **0.0791**

### Training Behavior
- Loss decreased steadily from 1.26 → 0.079
- Model converged smoothly
- No signs of instability or divergence

---

## Insights

- CNN learns spatial patterns effectively on satellite imagery
- Additional training significantly improves performance
- Model shows strong baseline performance for further improvements

---

## Current Status

- Classical CNN baseline completed
- Training pipeline implemented
- Evaluation pipeline working
- Preparing for hybrid quantum-classical experiments (PennyLane)

---

## Next Steps

- Improve CNN with Batch Normalization
- Add data augmentation
- Experiment with deeper architectures (ResNet-style)
- Implement Variational Quantum Classifier (VQC)
- Compare classical vs quantum performance

---

## 📁 Project Structure
