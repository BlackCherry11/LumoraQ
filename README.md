# LumoraQ

Quantum Machine Learning for Satellite Image Analysis

---

## Goal

This project investigates hybrid quantum-classical machine learning methods for Earth observation using the EuroSAT dataset.

The current stage focuses on building a strong classical baseline and validating a working Variational Quantum Classifier (VQC) before integrating both into a hybrid pipeline.

Rather than assuming quantum advantage, the project benchmarks classical deep learning against quantum and hybrid approaches.

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

## Classical Model (StrongCNN)

A Convolutional Neural Network was used as the classical benchmark:

- Conv2D (3 → 32)
- Batch Normalization
- ReLU
- Conv2D (32 → 32)
- Batch Normalization
- ReLU
- MaxPooling
- Conv2D (32 → 64)
- Batch Normalization
- ReLU
- Conv2D (64 → 64)
- Batch Normalization
- ReLU
- MaxPooling
- Fully Connected (16384 → 256)
- Dropout (0.4)
- Fully Connected (256 → 10)
- CrossEntropy Loss
- Adam Optimizer

---

## Classical Results

- Accuracy: 88.83%
- Precision (weighted): 89%
- Recall (weighted): 89%
- F1 Score (weighted): 89%

Test set size: 5,400 images

---

## Quantum Machine Learning (VQC Experiment)

A Variational Quantum Circuit was implemented using PennyLane.

---

### Quantum Circuit Design

- 2-qubit quantum system
- Input encoded using RX and RY rotation gates
- Measurements using Pauli-Z expectation values
- Trainable parameters optimized via gradient descent

Example:

Input: [0.5, 0.2]

Output:
[0.8775, 0.9800]

---

### VQC Training Setup

- Gradient descent optimizer (PennyLane)
- Trainable parameters initialized randomly
- Loss function defined over circuit outputs
- 100 optimization steps

---

### Training Results

Loss convergence:

- Initial loss: ~1.63
- Step 20: 0.0303
- Step 40: 0.0185
- Step 60: 0.0160
- Step 80: 0.0153
- Step 100: 0.0150

---

### Observations

- Quantum circuit parameters successfully optimized
- Gradient-based training worked as expected
- Loss decreased consistently over iterations
- The model demonstrates valid VQC learning behavior
- However, it is trained on simplified inputs, not satellite images yet

---

## Research Direction

The project now focuses on building a hybrid model:

CNN feature extractor  
→ feature compression  
→ quantum variational circuit  
→ final classification

The goal is to evaluate whether quantum layers provide measurable benefit compared to a strong classical baseline.

---

## Next Steps

- Extract intermediate features from StrongCNN
- Reduce dimensionality (PCA or similar)
- Feed features into quantum circuit
- Build hybrid CNN + VQC model
- Benchmark hybrid model against 88.83% baseline
