# Online Phase – Stream Learning Evaluation

## 📌 Description

The online phase simulates real-time classification using a Stream Learning approach.

Models are evaluated incrementally as new windows are received, allowing performance monitoring over time.

---

## 🔄 Online Workflow

1. Receive windowed data stream
2. Predict activity
3. Compare with true label (if available)
4. Update performance metrics incrementally
5. Analyze stability and reaction behavior

---

## 📂 Structure

### `online/notebooks/`
- **`app.ipynb`**  
  Main orchestration notebook. Demonstrates the end-to-end online workflow:
  streaming windows → prediction → persistence → selective label request → incremental updates.

- **`policy.ipynb`**  
  Implements the **label-request policy** (e.g., confidence thresholds, budget constraints, rules).
  Outputs decisions like: *request label* vs *skip* for each window.

- **`Calibradoripynb.ipynb`** (Calibrator)  
  Builds or applies a **probability/confidence calibration layer** for the baseline classifier (SVM).  
  Goal: make confidence values more reliable so the policy can request labels only when uncertainty is high.

- **`buscador_hiperparametros.ipynb`** (Hyperparameter search)  
  Searches/tunes key hyperparameters (e.g., thresholds for policy, incremental learner parameters, window settings).  
  Produces the best configuration used in the final online evaluation.

- **`Schema_json.ipynb`**  
  Generates/validates the JSON schema used to define the structure of streamed windows (features + metadata).
  Ensures consistency between client output and server ingestion.

- **`Analisis_Pruebas_Finales_SL.ipynb`**  
  Final analysis notebook for the Stream Learning experiments.
  Produces the plots and tables found in `online/results/` (learning curves, stability/reaction metrics, confusion matrices).

### `online/data_stream/`
Contains assets required for the online pipeline:
- `schema.json`: window schema (features + metadata).
- model artifacts (if lightweight): baseline classifier and calibrator.
- **Large stream files are not tracked** (e.g., full `windows.csv`) due to GitHub size limits. Use samples instead.

### `online/results/`
Exported evaluation artifacts:
- confusion matrices (HT / ARF / baseline SVM)
- learning curves overlays
- stability & reaction plots
- summary CSV tables (executive summary, per-class metrics, session stability)

---

## 📊 Online Evaluation Metrics

- Incremental Accuracy
- Stability
- Reaction Time
- Learning Curves
- Per-Class Metrics
- Confusion Matrices

---

## 📈 Performance Analysis

The online evaluation compares:

- Adaptive Random Forest (ARF)
- Hoeffding Tree (HT)
- Offline-trained SVM

The system analyzes:

- Model stability across sessions
- Adaptation speed
- Robustness to class changes
