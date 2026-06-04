# Progress Log - LumoraQ

## June 4

---

## Dataset
- EuroSAT dataset loaded
- 27,000 satellite images
- 10 classes
- Images resized to 64×64

---

## Model Development

### CNN Baseline Built
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
- Final Accuracy: 80.28%
- Final Loss: 0.0791

---

### Experiment 3 - StrongCNN Upgrade

#### Architecture Improvements

To improve classification performance, the original CNN architecture was upgraded with several modern deep learning techniques:

- Added Batch Normalization layers after convolution layers
- Increased network depth from 2 convolution layers to 4 convolution layers
- Increased feature channels from 16/32 to 32/64
- Added Dropout (0.4) before the classifier
- Added data augmentation:
  - RandomHorizontalFlip
  - RandomRotation (20°)
  - ColorJitter

#### Training

- Epochs: 15
- Optimizer: Adam
- Learning Rate: 0.0005

#### Results

- Final Accuracy: 88.83%

#### Improvement

- Initial CNN (1 Epoch): 67.61%
- Original CNN (15 Epochs): 80.28%
- StrongCNN (15 Epochs): 88.83%

Accuracy gain over previous model:
- +8.55 percentage points

Accuracy gain over initial baseline:
- +21.22 percentage points

#### Observations

- Batch Normalization improved training stability.
- Additional convolution layers improved feature extraction.
- Data augmentation improved generalization performance.
- StrongCNN is currently the best-performing model in the project.
- The model demonstrates that architectural improvements have a larger impact than simply increasing training epochs.

## Observations

- Increasing training epochs improved performance from 67.61% to 80.28%.
- Architectural improvements increased performance further to 88.83%.
- Batch Normalization stabilized training and improved convergence.
- Data augmentation improved model generalization.
- Deeper convolution layers extracted richer spatial features from satellite imagery.
- StrongCNN currently serves as the project's benchmark classical model.
---

## Confusion Matrix Analysis

Completed

Observations:

- Forest achieved perfect recall (1.00), indicating all forest images were successfully identified.
- SeaLake demonstrated the strongest overall classification performance.
- Residential and Industrial classes achieved high precision and recall.
- Most classification errors occurred among vegetation-related classes:
  - AnnualCrop
  - HerbaceousVegetation
  - PermanentCrop
  - Pasture

This suggests that spectrally similar land-cover categories remain challenging even for deep convolutional models.

## Next Steps

- Save and version-control trained model checkpoints
- Generate training and accuracy visualizations
- Compare multiple CNN architectures
- Implement a hybrid quantum-classical neural network
- Build a Variational Quantum Classifier (VQC)
- Compare quantum models against the 88.83% StrongCNN benchmark


