# Data Collection System and Stream Learning Model for ADL Classification

## 📌 Overview

This repository contains the complete implementation of the thesis project:

**"Data Collection System for Training a Stream Learning Model for Activities of Daily Living (ADL) Classification"**

The system was designed to support real-time classification of human activities using inertial data collected from smartphones.

The project is structured in two main phases:

- Offline phase (data preparation and model training)
- Online phase (real-time incremental classification)

---

## 🎯 Objective

To design and implement a client-server architecture capable of:

- Collecting inertial sensor data (accelerometer and gyroscope)
- Segmenting data into temporal windows
- Training supervised models (SVM, Random Forest)
- Deploying an incremental Stream Learning model
- Performing real-time classification of ADL
- Evaluating stability and reaction performance

---

## 🏗 System Architecture

The system is divided into two main components:

### 🔹 Offline Phase
- Data cleaning and preprocessing
- Window segmentation
- Class balancing strategies (Random, SMOTE)
- Model training and evaluation
- Model selection and export

### 🔹 Online Phase
- Continuous window streaming
- Real-time classification
- Incremental evaluation
- Stability and reaction analysis

---
## 📂 Repository Structure
offline/
  notebooks/
  data_processed/
  models/
    balanced/
    unbalanced/
    final/

online/
  notebooks/
  data_stream/
  results/

---

## 📊 Key Results

- Final selected model: **SVM - Pocket position - 20Hz**
- Comparison against Random Forest
- Incremental evaluation using River
- Stability and reaction performance analysis
- Per-class performance metrics

---

## ⚙️ Technologies Used

- Python
- Scikit-learn
- River (Stream Learning)
- Pandas
- NumPy
- Matplotlib
- SMOTE (Imbalanced-learn)

---

## 👩‍🔬 Author

Paula M.  
Electronic and Telecomunication Engineering 
Universidad del Cauca  

---

## 📜 License

This project is intended for academic and research purposes.


