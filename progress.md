# Progress Log - LumoraQ

---

## 1. Dataset

- EuroSAT dataset loaded
- 27,000 images
- 10 classes
- Image size: 64×64
- Normalization applied

---

## 2. Classical Model Development

### 2.1 Initial CNN

- 2 convolution layers
- MaxPooling
- Fully connected classifier
- CrossEntropyLoss
- Adam optimizer

Accuracy:
- 67%

---

### 2.2 Extended Training

- Same model trained longer

Accuracy:
- 80.28%

Loss:
- 0.0791

---

### 2.3 StrongCNN

Architecture upgrades:
- Batch Normalization
- Increased depth (2 → 4 conv layers)
- Increased channels (16/32 → 32/64)
- Dropout (0.4)
- Data augmentation:
  - RandomHorizontalFlip
  - RandomRotation
  - ColorJitter

Training:
- Epochs: 15
- Learning rate: 0.0005

---

## 3. Final Classical Results

- Accuracy: 88.83%
- Precision: 89%
- Recall: 89%
- F1 Score: 89%

Loss:
- 0.0791

---

## 4. Training Graphs

Generated:
- Accuracy vs Epoch
- Loss vs Epoch

Observations:
- Stable convergence
- No overfitting due to augmentation + dropout
- Validation closely follows training curve

---

## 5. Confusion Matrix

### 5.1 Diagonal Dominance

Strong diagonal entries indicate correct predictions across most classes.

---

### 5.2 Best Performing Classes

- Forest
- SeaLake
- Residential
- Industrial

---

### 5.3 Weak Classes

- AnnualCrop
- HerbaceousVegetation
- PermanentCrop
- Pasture

---

### 5.4 Insight

- Errors are structured, not random
- Vegetation classes overlap in feature space
- Model generalizes well for distinct land types

---

## 6. Quantum Machine Learning (VQC)

### 6.1 Circuit

- 2-qubit variational quantum circuit
- RX and RY encoding
- Pauli-Z measurement
- Trainable parameters

---

### 6.2 Training

Optimizer:
- Gradient Descent (PennyLane)

Steps:
- 100 iterations

---

### 6.3 Loss Progression

- Initial: ~1.6395
- Step 20: 0.030337
- Step 40: 0.018537
- Step 60: 0.016034
- Step 80: 0.015287
- Step 100: 0.015035

---

### 6.4 Observations

- Smooth convergence
- Stable optimization
- Valid quantum gradient computation
- Toy model successfully learned
- Not yet integrated with real dataset

---

## 7. Current Status

Classical:
- StrongCNN complete (88.83%)

Quantum:
- VQC implemented and trained
- Convergence verified

---

## 8. Next Steps

- Extract CNN features
- Apply PCA
- Feed into quantum circuit
- Build hybrid CNN + VQC model
- Benchmark against classical model