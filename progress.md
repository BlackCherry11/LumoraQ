# Progress Log - LumoraQ

---

## June 2026

---

## Dataset

- EuroSAT dataset loaded
- 27,000 images
- 10 land-use classes
- Images resized to 64×64

---

## Model Development

### CNN Baseline

- 2 convolution layers
- MaxPooling layers
- Fully connected classifier
- CrossEntropy loss
- Adam optimizer

---

## Experiments

### Experiment 1 - Initial Training
- Epochs: 1
- Accuracy: 67%
- Loss: 1.2602

---

### Experiment 2 - Extended Training
- Epochs: 15
- Accuracy: 80.28%
- Loss: 0.0791

---

### Experiment 3 - StrongCNN Upgrade

Architecture Improvements:
- Batch Normalization added
- Depth increased (2 → 4 conv layers)
- Channels increased (16/32 → 32/64)
- Dropout (0.4)
- Data augmentation:
  - RandomHorizontalFlip
  - RandomRotation
  - ColorJitter

Training Setup:
- Epochs: 15
- Optimizer: Adam
- Learning rate: 0.0005

---

## Final Results

- Accuracy: 88.83%
- Precision (weighted): 89%
- Recall (weighted): 89%
- F1 Score (weighted): 89%

Improvement:
- 67% → 80.28% → 88.83%

---

## Observations

- Batch Normalization improved convergence stability
- Deeper networks improved feature extraction
- Data augmentation improved generalization
- Vegetation-related classes remain the hardest to classify
- StrongCNN is the current benchmark model

---

## Confusion Matrix Insights

- Forest achieved perfect recall (1.00)
- SeaLake performed best overall
- Residential and Industrial classes performed strongly
- Confusions mostly occur among vegetation classes:
  - AnnualCrop
  - HerbaceousVegetation
  - PermanentCrop
  - Pasture

These classes remain spectrally similar and difficult to separate.

---

## Research Direction

The project now transitions toward quantum machine learning.

Goal:

Evaluate whether hybrid quantum-classical models can compete with deep CNNs in satellite image classification.

Focus is on:
- empirical evaluation
- benchmarking
- hybrid architecture exploration

---

## Next Steps

- Save model checkpoints (.pth versioning)
- Create training curves and visualizations
- Compare CNN architectures (ResNet, etc.)
- Implement Variational Quantum Classifier (VQC)
- Build CNN → Quantum hybrid pipeline
- Benchmark against StrongCNN (88.83%)

---
