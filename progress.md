# Progress Log - LumoraQ

## June 4

---

## 📊 Dataset
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

## Observations

- Model improves significantly with more training epochs
- Loss decreases smoothly without instability
- CNN effectively learns spatial features of satellite images
- No overfitting observed yet at this stage

---

## 🚀 Next Steps

- Improve model architecture (BatchNorm, deeper CNN)
- Add data augmentation
- Optimize hyperparameters
- Begin quantum model implementation using PennyLane
