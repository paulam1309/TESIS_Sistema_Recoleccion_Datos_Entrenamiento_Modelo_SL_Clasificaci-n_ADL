# Offline Phase – Model Training and Evaluation

## 📌 Description

The offline phase focuses on data preparation, feature engineering, model training, and selection of the optimal model for deployment in the online Stream Learning phase.

---

## 🔬 Pipeline

1. Data cleaning and preprocessing
2. Noise filtering
3. Window segmentation (20Hz and 50Hz)
4. Feature extraction
5. Class balancing:
   - Random oversampling
   - SMOTE
6. Model training:
   - Support Vector Machine (SVM)
   - Random Forest (RF)
7. Model evaluation and comparison
8. Export of the final selected model

---

## 📂 Structure
notebooks/
  PREPARACION-DEL-DATASET.ipynb
  MODELADO_RF_SVM.ipynb
  PREPARACION_PARA_SL.ipynb
data_processed/
  windowed datasets
models/
  balanced/
  unbalanced/
  final/
  
---

## 🧠 Model Selection

After evaluating multiple configurations (position and frequency), the final selected model was:

**SVM – Pocket position – 20Hz**

This model showed the best trade-off between performance and generalization capability.

---

## 📊 Evaluation Metrics

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

