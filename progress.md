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

## Classical Model Development

### CNN Baseline

- 2 convolution layers
- MaxPooling layers
- Fully connected classifier
- CrossEntropy loss
- Adam optimizer

---

### StrongCNN Upgrade

Architecture improvements:
- Batch Normalization added
- Depth increased (2 → 4 conv layers)
- Channels increased (16/32 → 32/64)
- Dropout (0.4)
- Data augmentation:
  - RandomHorizontalFlip
  - RandomRotation
  - ColorJitter

Training:
- Epochs: 15
- Learning rate: 0.0005

---

## Classical Results

- Initial CNN: 67%
- Extended CNN: 80.28%
- StrongCNN: 88.83%

Final metrics:
- Precision (weighted): 89%
- Recall (weighted): 89%
- F1 Score (weighted): 89%

---

## Observations (Classical)

- Batch Normalization improved stability
- Deeper networks improved feature extraction
- Data augmentation improved generalization
- StrongCNN is current benchmark model

---

## Quantum Machine Learning (VQC Experiment)

### Quantum Circuit

- 2-qubit Variational Quantum Circuit
- RX and RY encoding for inputs
- Pauli-Z expectation measurements
- Trainable parameters optimized via gradient descent

---

### Training Behavior

Initial tests confirmed successful learning:

- Initial loss: ~1.63
- Step 20: 0.0303
- Step 40: 0.0185
- Step 60: 0.0160
- Step 80: 0.0153
- Step 100: 0.0150

---

### Observations (Quantum)

- Circuit is fully differentiable
- Gradient descent optimization works correctly
- Parameters converge to stable minimum
- Model is functional as a basic VQC
- Currently operates on synthetic inputs, not satellite images

---

## Key Insight

Quantum model is valid but not yet integrated with real dataset.

---

## Next Steps

- Extract CNN feature vectors from StrongCNN
- Apply dimensionality reduction (PCA)
- Feed features into quantum circuit
- Build hybrid CNN + VQC architecture
- Benchmark against 88.83% classical model
