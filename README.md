![image](https://github.com/user-attachments/assets/35995544-6526-4154-9d48-707fb2613628)

# 🌿 Plant-Seedlings-Classification

## 🔍 Overview

- **Task**: Image classification – predict plant species from seedling images
- **Dataset**: 5,475 training images across 12 categories (e.g. Sugar beet, Maize, Loose Silky-bent), plus 794 unlabeled test images
- **Framework**: TensorFlow / Keras
- **Model**: Simple CNN with 3 convolutional blocks + BatchNorm + Dropout
- **Augmentation**: Rotation, zoom, shift, brightness, flip
- **Performance**:  
  - Validation Accuracy: **73.5%**  
  - Final Kaggle Score: **0.76826**

---

🚀 Project Steps
Exploratory Data Analysis

Visualized class imbalance in train/

Previewed sample images by class

Image Preprocessing

Resized all images to 224x224

Normalized pixel values to [0, 1]

Applied data augmentation using ImageDataGenerator

Model 1: Simple CNN

3 Conv2D blocks (Conv → BatchNorm → MaxPooling)

Dense(256) + Dropout(0.5)

Output: Dense(12, softmax)

Optimizer: Adam, Loss: categorical_crossentropy

Model 2: MobileNetV2

Pretrained on ImageNet, top removed

Frozen all convolutional layers

Added custom dense head: GAP → Dropout(0.3) → Dense(512) → Dense(12, softmax)

Used Adam(lr=1e-4) for stable fine-tuning

Training & Evaluation

Used EarlyStopping and ModelCheckpoint

Compared accuracy/loss curves across both models

MobileNetV2 outperformed the custom CNN

Kaggle Submission

Simple CNN: accuracy = 71.91%

MobileNetV2: accuracy = 76.70% ✅

