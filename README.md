# LumoraQ

Quantum Machine Learning for Satellite Image Analysis

---

## Goal

This project investigates hybrid quantum-classical machine learning methods for Earth observation data using the EuroSAT dataset.

The current stage focuses on building a strong classical baseline before introducing quantum models.

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
- StrongCNN architecture implemented
- Training and evaluation pipeline completed
- Best accuracy achieved: 88.83%
- Preparing for hybrid quantum-classical experiments using PennyLane

---

## Training Results

## StrongCNN Upgrade

To improve performance, the original CNN was upgraded with:

- Batch Normalization
- Deeper convolutional architecture
- Dropout regularization
- Data augmentation

Techniques used:

- RandomHorizontalFlip
- RandomRotation
- ColorJitter

### Best Result

Accuracy: **88.83%**

Improvement over original CNN:

80.28% → 88.83%

Improvement over initial baseline:

67% → 88.83%

## Latest Results

StrongCNN Evaluation Results:

| Metric | Value |
|----------|----------|
| Accuracy | 88.83% |
| Precision (Weighted Avg) | 89% |
| Recall (Weighted Avg) | 89% |
| F1 Score (Weighted Avg) | 89% |

Test Dataset Size: 5400 Images

The model demonstrates strong performance across all ten EuroSAT land-cover classes and serves as the current classical benchmark for subsequent quantum experiments.

## Key Findings

- Deep CNN architectures significantly outperform shallow CNN baselines.
- Architectural improvements contributed more to performance gains than increasing training epochs alone.
- Batch Normalization improved convergence and training stability.
- Data augmentation improved model generalization on unseen satellite imagery.
- Certain land-cover classes such as SeaLake and Residential achieved near-perfect classification performance.
- Visually similar vegetation classes remain the most challenging classification task.

## Research Direction

The next stage of the project investigates whether Quantum Machine Learning can provide advantages for Earth observation tasks.

The primary research question is:

Can hybrid quantum-classical machine learning models effectively analyze high-dimensional satellite imagery and provide competitive performance compared to modern deep learning approaches?

Rather than assuming quantum superiority, the project aims to benchmark and evaluate the practical strengths and limitations of quantum machine learning in remote sensing applications.

## Next Steps

- Save and version trained model checkpoints
- Generate training and accuracy visualizations
- Experiment with ResNet-style architectures
- Install PennyLane
- Implement a Variational Quantum Classifier (VQC)
- Compare hybrid quantum-classical models against the 88.83% StrongCNN benchmark

---

## Project Structure
