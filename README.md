# Facial_Emotion_Recognition

## Project Overview
Facial Emotion Recognition (FER) is an important task in computer vision that aims to automatically identify human emotions from facial expressions.
This project uses Convolutional Neural Networks (CNNs) and transfer learning with popular pre-trained models such as MobileNetV2 to classify emotions from facial images.
The workflow includes:
Data preprocessing and augmentation to improve model generalization
Model training using multiple architectures for performance comparison
Performance evaluation using accuracy and loss curves

## 1) Data Augmentation for Class Balancing
Since the fer2013 dataset is imbalanced (some emotions like happy are overrepresented, while others like disgust or fear have fewer samples), this project applies targeted data augmentation to underrepresented classes.
#### Key Steps:
##### Copy Training Data:
The original training dataset is duplicated into a new folder (fer_aug_dataset) to avoid modifying the original files.
##### Target Classes for Augmentation:
Emotion categories with fewer samples were selected: sad, angry, surprise.
##### Augmentation Techniques Applied:
Random rotations (±20°)
Width and height shifts (±10%)
Zoom transformations (±10%)
Horizontal flips
Filling gaps with nearest-pixel interpolation

## Implemented Models
This project explores and compares multiple deep learning architectures for Facial Emotion Recognition. The goal was to evaluate how different CNN depths and transfer learning strategies affect model performance.
##### 1)Custom 10-Layer CNN Model (Chosen Model)
##### 2)Custom 12-Layer CNN Model 
##### 3)Custom 16-Layer CNN Model 
##### 4)MobileNetV2 Model
##### 5)MobileNetV2 with Fine-Tuning (Last 30 Layers)

##📈 Results & Performance
The following table summarizes the performance of the implemented models on the validation set:
| Model                                   | Train Accuracy | Validation Accuracy | Train Loss | Validation Loss | Notes                                                 |
| --------------------------------------- | -------------- | ------------------- | ---------- | --------------- | ----------------------------------------------------- |
| **Custom 10-Layer CNN**                 | **68.97%**     | **63.98%**          | **0.8438** | **0.9746**      | ✅ Best trade-off, chosen as final model              |
| Custom 12-Layer CNN                     | 68%            | 63%                 | 0.8445     | 0.9755          | Similar to 10-layer, slightly less stable             |
| Custom 16-Layer CNN                     | 51.61%         | 53.35%              | 1.2755     | 1.2221          | Underfitting, deeper network didn’t improve           |
| MobileNetV2                             | 65.13%         | 60.41%              | 0.9338     | 1.0560          | Efficient, but lower validation performance           |
| MobileNetV2 (Fine-tuned last 30 layers) | 71.60%         | 62.56%              | 0.7539     | 1.0703          | Better than vanilla MobileNetV2,but still weaker than 10-layer CNN | 

## Performance Analysis
Plotting the accuracy and loss of the trained model is always the first step to anaylze how the the model is performing. Here are two pictures illustrating the difference in performance between MobileNetV2 fine-tuned architecture and the 10-Layer CNN architecture.

