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
### `offline/notebooks/`
- **`PREPARACION-DEL-DATASET.ipynb`**  
  Loads the raw offline sensor captures, performs cleaning, basic preprocessing and generates the consolidated dataset used for training.

- **`MODELADO_RF_SVM.ipynb`**  
  Trains and compares **Random Forest** and **SVM** across different configurations (device position and sampling rate).  
  Includes evaluation metrics (accuracy/precision/recall/F1, confusion matrix) and supports the final model decision.

- **`PREPARACION PARA SL.ipynb`**  
  Converts the selected offline dataset into **windowed files** compatible with the online Stream Learning stage (window segmentation + export).  
  Produces the window datasets used for streaming and incremental evaluation.

### `offline/data_raw/`
Raw offline captures (not always included in the repo if they are large).  
If removed for size/privacy, this folder may contain only a sample and instructions to reproduce the full dataset.

### `offline/data_processed/`
Processed datasets and windowed files (CSV/XLSX).  
Recommended: keep only lightweight samples + final summary files in the repo.

### `offline/models/`
- `balanced/`: models trained on balanced data (Random oversampling / SMOTE).
- `unbalanced/`: models trained on the original class distribution.
- `final/`: the final selected model artifact(s) used as baseline for the online phase.

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

