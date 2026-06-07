# LumoraQ

Quantum Machine Learning for Satellite Image Analysis

---

## Goal

This project investigates hybrid quantum-classical machine learning methods for Earth observation using the EuroSAT dataset.

The current stage focuses on building a strong classical baseline before introducing quantum models.

Rather than assuming quantum advantage, the project benchmarks classical deep learning against hybrid quantum approaches.

---

## Dataset

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

## Model Architecture

A Convolutional Neural Network (CNN) was implemented as the classical baseline:

- Conv2D (3 → 32 filters)
- Batch Normalization
- ReLU
- Conv2D (32 → 32 filters)
- Batch Normalization
- ReLU
- MaxPooling
- Conv2D (32 → 64 filters)
- Batch Normalization
- ReLU
- Conv2D (64 → 64 filters)
- Batch Normalization
- ReLU
- MaxPooling
- Fully Connected (16384 → 256)
- Dropout (0.4)
- Fully Connected (256 → 10)
- CrossEntropy Loss
- Adam Optimizer

---

## Training Results

### Baseline CNN
- Epochs: 1
- Accuracy: 67%
- Loss: 1.2602

### Extended Training
- Epochs: 15
- Accuracy: 80.28%
- Loss: 0.0791

### StrongCNN (Final Model)
- Accuracy: 88.83%
- Precision (Weighted): 89%
- Recall (Weighted): 89%
- F1 Score (Weighted): 89%

Test set size: 5,400 images

---

## Key Improvements

- 80.28% → 88.83% after architecture upgrade
- 67% → 88.83% overall improvement

Key factors:
- Batch Normalization improved stability
- Deeper CNN improved feature extraction
- Data augmentation improved generalization
- Dropout reduced overfitting

---

## Insights

- CNNs effectively learn spatial patterns in satellite imagery
- Architectural improvements outperform simple epoch scaling
- Vegetation-related classes remain the most difficult to separate
- Visually similar land-cover classes lead to classification overlap

---

## Research Direction

The next phase explores whether Quantum Machine Learning can enhance performance on remote sensing tasks.

Core research question:

Can hybrid quantum-classical models compete with or improve upon modern deep learning methods for satellite image classification?

This project aims to evaluate quantum ML pragmatically, focusing on empirical comparison rather than assumed advantage.

---

## Next Steps

- Save and version trained models
- Generate training and accuracy plots
- Experiment with ResNet-based architectures
- Implement Variational Quantum Classifier (VQC)
- Build hybrid CNN + quantum pipeline
- Benchmark quantum models against StrongCNN (88.83%)

---
