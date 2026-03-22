# Acoustic Drone Detection Using Deep Learning
### Using Machine Learning for passive defense against aerial attacks and privacy violations

**Author: Abel Chuchu | UAE | March 2026**

---

## Motivation

Recent military tensions in the Middle East sparked my interest in exploring how machine learning could be applied to real-world security and civil defense scenarios. Compared to large threats like cruise missiles or ballistic missiles, many drones are much more difficult to detect because they are small, fly at very low altitudes, and often avoid radar detection.

However, many drones produce distinctive acoustic signatures due to their propellers or engines. Some military drones are often described as sounding like a “moped” or “lawnmower”. This led me to explore whether machine learning could be used to detect drones using sound alone as a passive detection method.

Currently, there is no public dataset that includes audio recordings of military drones such as the Shahed-131, Shahed-136, Shahed-129, or similar UAVs. Therefore, this project uses the largest public drone audio dataset available to build a **proof-of-concept acoustic drone detection system**.

This project is not intended to be a deployable system, but rather a demonstration of the machine learning pipeline and the feasibility of sound-based drone detection.

---

## Project Overview

This project builds a binary classification model that classifies audio as:

**Drone** or **No Drone**

The system works by converting audio into Mel-Spectrogram images and training a Convolutional Neural Network (CNN) to recognize acoustic patterns associated with drones.

---

## What This Notebook Does

1. Loads drone and non-drone audio data
2. Preprocesses audio (resampling, trimming, normalization)
3. Converts audio into Mel-Spectrograms
4. Trains a deep learning model (CNN / ResNet18)
5. Evaluates performance on unseen test data
6. Provides a demo interface where users can upload audio for prediction
7. Visualizes spectrograms and model predictions

This notebook demonstrates the **full machine learning pipeline** from raw audio to prediction.

---

## Dataset

**DADS — Drone Audio Detection Samples (HuggingFace)**  
Contains drone and non-drone audio recordings.

- Format: WAV
- Sampling rate: 16,000 Hz
- Mono channel
- Label 0 = No Drone
- Label 1 = Drone
- Includes background noise such as traffic, wind, and urban sounds

Dataset Link:  
https://huggingface.co/datasets/geronimobasso/drone-audio-detection-samples

Due to computational limitations, a **subset of the dataset** was used for training in this proof-of-concept.

---

## System Pipeline
Audio Input
↓
Audio Preprocessing
↓
Feature Extraction (Mel Spectrogram)
↓
Deep Learning Model (CNN / ResNet18)
↓
Binary Classification (Drone / No Drone)
↓
Evaluation
↓
Interactive Demo Interface




---

## Tools and Libraries

- Python
- Google Colab
- PyTorch
- Librosa
- NumPy
- Matplotlib
- Scikit-learn
- Seaborn
- Gradio (for demo interface)

**Hardware:** Google Colab T4 GPU

---

## Results (Proof of Concept)

The model is able to learn acoustic patterns associated with commercial electric drones and can distinguish drone audio from background noise in many cases. This demonstrates that **acoustic signals can be used as a feature for drone detection**.

This is a **proof-of-concept model**, and performance is limited by dataset diversity and computational constraints.

---

## Important Limitations

- Dataset contains mostly **commercial electric drones**
- No military drone audio in the dataset
- Trained on a **subset** of the dataset
- Possible **overfitting** to specific acoustic signatures
- Limited hyperparameter tuning
- Real-world conditions (distance, wind, microphone quality) will affect performance

This project should be viewed as a **concept demonstration**, not a production system.

---

## Future Work

- Train on larger and more diverse datasets
- Include different drone types (including fixed-wing and engine drones)
- Multi-class classification (drone type identification)
- Real-time detection using live microphone input
- Combine acoustic detection with camera or radar systems
- Build a larger custom drone audio dataset

---

by **Abel Chuchu**  
UAE  
March 2026
