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

notebooks/
  app.ipynb
  policy.ipynb
  buscador_hiperparametros.ipynb
  Analisis_Pruebas_Finales_SL.ipynb
  Calibrador.ipynb
  
data_stream/
  schema.json
  model.pkl

results/
  confusion matrices
  learning curves
  stability metrics
  reaction analysis
  
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
