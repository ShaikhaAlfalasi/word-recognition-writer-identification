# Handwritten Word Recognition and Writer Identification Using CNNs

A deep learning-based system for handwritten word recognition and writer identification using Convolutional Neural Networks (CNNs). This project combines computer vision, image preprocessing, and neural network architectures to analyze handwritten text and identify writing styles in both closed-set and open-set scenarios.

Developed as a final project for Topics in Computer Science II at the University of Sharjah.

---

## Project Overview

This project consists of two deep learning models:

### 1. Handwritten Word Recognition Model
A CNN-based handwritten text recognition pipeline capable of predicting handwritten English words from image inputs.

The model:
- Segments handwritten words into individual characters
- Uses a custom CNN model (CharCNN) for character classification
- Reconstructs complete words from predicted characters
- Applies dictionary-based spelling correction to improve final predictions

### 2. Writer Identification Model
A CNN-based writer classification model designed to identify which person wrote a handwritten sample based on handwriting characteristics such as:
- Stroke patterns
- Letter formation
- Character spacing
- Writing style

The model supports:

#### Closed-Set Writer Identification
The system classifies handwriting samples among the five known writers from our group.

#### Open-Set Writer Identification
The system can also detect handwriting from writers that were **not included during training**.

Instead of forcing an incorrect prediction, the model can classify a sample as "Unknown Writer".

This was implemented using:
- Prototype embeddings
- Euclidean distance comparison
- Threshold-based rejection

allowing the model to reject unseen writers with a 90% unknown rejection rate.

---

## Features

- CNN-based handwritten character recognition
- Writer identification using deep learning embeddings
- Open-set recognition for unknown writers
- Character segmentation using contour detection
- Adaptive preprocessing pipeline
- Dictionary-based spelling correction
- Real-time web application deployment
- Custom handwritten dataset collected from team members

---

## Datasets

### EMNIST Letters Dataset
Used for pretraining the character recognition model.

- 145,600 grayscale handwritten letter images
- 26 English letter classes (a-z)
- Image size: 28×28

### Custom Handwritten Dataset
A custom dataset collected from the five group members.

Dataset characteristics:
- Handwritten word images in `.png` format
- Multiple handwriting styles
- Separate training and testing sets
- Used for:
  - Word recognition fine-tuning
  - Writer identification training
  - Open-set evaluation

---

## Results

### Word Recognition Performance
- Character-level accuracy on EMNIST: **93.61%**
- Character-level accuracy on custom dataset: **79.69%**
- Word-level accuracy on custom dataset: **66.67%**

### Writer Identification Performance
#### Closed-Set Evaluation
- Accuracy: **93.33%**
- Macro F1-score: **0.9314**

#### Open-Set Evaluation
- Unknown writer rejection rate: **90%**
- Known writer acceptance rate: **83.33%**

The system successfully identified unseen handwriting samples as unknown rather than misclassifying them as one of the known writers.

---

## Technologies Used

- Python
- PyTorch
- OpenCV
- NumPy
- PIL
- scikit-learn
- Matplotlib
- pyspellchecker

---

## Web Application

The final system was integrated into a web application for real-time handwriting analysis and deployed in April 2026.
Web application link: https://handwriting-recognition-ehq7.onrender.com/

---
