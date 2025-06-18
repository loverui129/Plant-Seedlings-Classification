![image](https://github.com/user-attachments/assets/35995544-6526-4154-9d48-707fb2613628)

# 🌿 Plant-Seedlings-Classification

## 🔍 Overview

- **Task**: Image classification – predict plant species from seedling images
- **Dataset**: 5,475 training images across 12 categories (e.g. Sugar beet, Maize, Loose Silky-bent), plus 794 unlabeled test images
- **Framework**: TensorFlow / Keras
- **Model**:

    - ✅ Model 1 – Simple CNN: 3 convolutional blocks + BatchNorm + Dropout

    - ✅ Model 2 – MobileNetV2: Pretrained on ImageNet with a custom dense head
- **Augmentation**: Rotation, zoom, shift, brightness, flip
- **Performance**:  
  - Validation Accuracy: **75.7%**  
  - Final Kaggle Score: **0.76700 ✅ (Best)**

---

## 🚀 Project Steps

1. **Exploratory Data Analysis**

  - Visualized class imbalance in train/
    
  - Previewed sample images by class

2. **Image Preprocessing**

  - Resized all images to 224x224
  
  - Normalized pixel values to [0, 1]
  
  - Applied data augmentation using ImageDataGenerator

3. **Model 1: Simple CNN**

  - 3 Conv2D blocks (Conv → BatchNorm → MaxPooling)
  
  - Dense(256) + Dropout(0.5)
  
  - Output: Dense(12, softmax)
  
  - Optimizer: Adam, Loss: categorical_crossentropy

4. **Model 2: MobileNetV2**

  - Pretrained on ImageNet, top removed
    
  - Frozen all convolutional layers
    
  - Added custom dense head: GAP → Dropout(0.3) → Dense(512) → Dense(12, softmax)
    
  - Used Adam(lr=1e-4) for stable fine-tuning

5. **Training & Evaluation**

  - Used EarlyStopping and ModelCheckpoint
    
  - Compared accuracy/loss curves across both models
    
  - MobileNetV2 outperformed the custom CNN

6. **Kaggle Submission**

  - Simple CNN: accuracy = 71.91%
    
  - MobileNetV2: accuracy = 76.70% ✅

