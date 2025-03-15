# Image Classification: Enhancing CIFAR-10 Performance with Modified ResNet

**CS-GY 6953 / ECE-GY 7123 Deep Learning Mini-Project Spring 2025**  
**New York University (NYU) Tandon School of Engineering**

---

## Overview

This repository contains the implementation of a **Modified ResNet Architecture** for image classification on the **CIFAR-10 dataset**. The goal of this project is to achieve **>better test accuracy** while keeping the model under **5 million trainable parameters**.

---

## Model Architecture

The model is based on the **ResNet (Residual Network)** framework, which uses residual blocks to improve training efficiency for deep networks. Key modifications include:
- **Custom BasicBlock** with dropout layers for regularization.
- Three main layers (`layer1`, `layer2`, `layer3`) with increasing feature maps (32, 64, 128).
- **Adaptive Average Pooling** followed by a fully connected layer for classification.
- Total trainable parameters: **1,177,130**, well below the 5M constraint.

---

## Training Methodology

### **Framework**
- **PyTorch** with CUDA for GPU acceleration.

### **Data Augmentation**
- Random horizontal flips.
- Random cropping with padding.
- Normalization using CIFAR-10-specific mean and standard deviation values.

### **Optimizer**
- **Stochastic Gradient Descent (SGD)** with:
  - Momentum: 0.9
  - Weight decay: 3e-4

### **Learning Rate Scheduler**
- **MultiStepLR** with milestones at epochs `[90, 180, 240, 360]` and gamma=0.1.

### **Loss Function**
- CrossEntropyLoss.

### **Training Details**
- **Batch Size**: 128
- **Epochs**: 200

---

## Performance

### **Results**
- **Training Accuracy**: Reached **99.41%** by the 200th epoch.
- **Validation Accuracy**: Achieved a peak of **94.61%**.
- **Test Accuracy**: Achieved a peak of **84.161%**.

### **Metrics**
- Training and validation loss/accuracy were tracked and visualized for each epoch.

---

## References

1. Krizhevsky, A. (2009). Learning multiple layers of features from tiny images. [click here](https://www.cs.toronto.edu/~kriz/cifar.html)
2. He, K., Zhang, X., Ren, S., & Sun, J. (2015). Deep Residual Learning for Image Recognition. CoRR, abs/1512.03385. [click here](https://doi.org/10.48550/arXiv.1512.03385)
3. Shuvam Das (2023). Implementation of ResNet Architecture for CIFAR-10 and CIFAR-100 Datasets. [click here](https://medium.com/deepkapha-notes/tagged/architecture)
4. Liu, W. et al. (2021). Improvement of CIFAR-10 Image Classification Based on Modified ResNet-34. In: Meng, H., Lei, T., Li, M., Li, K., Xiong, N., Wang, L. (eds) Advances in Natural Computation, Fuzzy Systems and Knowledge Discovery. ICNC-FSKD 2020. Lecture Notes on Data Engineering and Communications Technologies, vol 88. Springer, Cham. [click here](https://doi.org/10.1007/978-3-030-70665-4_68)
5. Thakur, A., Chauhan, H., Gupta, N. (2023). Efficient ResNets: Residual Network Design. arXiv preprint, arXiv:2306.12100. [click here](https://arxiv.org/abs/2306.12100)
<br /> <br />

---

## Team Members
1. Bhanu Dileep Reddy Maryada | bm3689 <br />
2. Yaswanth Kumar Damarla | yd3034 <br />
3. Bhagya Rekha Deenadayal | bd2585 <br />
