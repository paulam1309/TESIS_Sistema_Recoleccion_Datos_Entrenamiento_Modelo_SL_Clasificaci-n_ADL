# Data Collection System and Stream Learning Model for ADL Classification

## 📌 Overview

This repository contains the complete implementation of the thesis project:

**"Data Collection System for Training a Stream Learning Model for Activities of Daily Living (ADL) Classification"**

The system was designed to support real-time classification of human activities using inertial data collected from smartphones (accelerometer and gyroscope).

The project integrates:

- Offline supervised training
- Online incremental (stream) learning
- Selective label request policy
- Stability and reaction analysis over time

The architecture follows a client–server model with persistent storage and incremental adaptation.

---

## 🎯 Objective

To design and implement a client-server architecture capable of:

- Collecting inertial sensor data from smartphones
- Segmenting data into temporal windows
- Training supervised models (SVM, Random Forest)
- Deploying an incremental Stream Learning model
- Performing real-time ADL classification
- Requesting labels selectively based on model uncertainty
- Evaluating stability and reaction performance over time

---

# 🏗 System Architecture

The system is divided into two major phases:

---

## 🔹 Offline Phase (Local Data Collection & Model Selection)

In the offline phase:

- Smartphones collect raw IMU signals.
- Data are stored locally and exported as CSV files.
- The dataset is cleaned and filtered.
- Signals are segmented into time windows (20Hz / 50Hz).
- Class balancing techniques are applied (Random Oversampling / SMOTE).
- Supervised models (SVM, Random Forest) are trained and compared.
- The best configuration is selected and exported as the baseline model.

### Offline Architecture

![Offline architecture](docs/architecture_offline.png)

---

## 🔹 Online Phase (Streaming & Incremental Learning)

In the online phase:

- The client app streams windowed data (features + metadata).
- The server receives and validates windows.
- A classification module generates predictions + confidence.
- A policy engine decides whether to request a label.
- Labeled windows are aligned and stored.
- An incremental learner (HT / ARF) updates the model continuously.
- Performance is monitored using learning curves, stability and reaction metrics.

### High-Level Client–Server Architecture

![Online architecture](docs/architecture_online_highlevel.png)

---

## 🔹 Detailed Server Modules

The server is divided into:

- Ingestion/Validation module
- Classification module
- Rule/Policy engine
- Label aligner
- Incremental trainer
- Database persistence

![Online detailed modules](docs/architecture_online_detailed.png)

---

## 🔹 Labeling & Incremental Training Pipeline

This diagram summarizes the internal decision flow:

1. Window → Baseline classifier (SVM + Calibrator)
2. Prediction + confidence → Policy engine
3. Label request (if needed)
4. Label alignment
5. Incremental update (HT / ARF)

![Policy and incremental learning pipeline](docs/policy_pipeline.png)

---

---

# 📊 Key Results

- Final selected offline model: **SVM – Pocket position – 20Hz**
- Comparative analysis against Random Forest
- Incremental evaluation using River
- Stability analysis across sessions
- Reaction time analysis after model updates
- Per-class performance metrics
- Learning curve overlays

---

# ⚙️ Technologies Used

- Python
- Scikit-learn
- River (Stream Learning)
- Pandas
- NumPy
- Matplotlib
- Imbalanced-learn (SMOTE)

---

# 🧠 Research Contributions

- Integration of offline supervised learning with online incremental adaptation
- Selective labeling strategy to reduce annotation burden
- Stability and reaction metrics for continuous evaluation
- End-to-end architecture from data collection to deployment simulation

---

# 👩‍🔬 Author

**Paula M.**  
Electronic and Telecommunications Engineering  
Universidad del Cauca  

---

# 📜 License

This project is intended for academic and research purposes.

