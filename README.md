
# 🏎️ F1 Pit Stop Prediction — Iterative ML System

## 📌 Overview

This project tackles the **prediction of Formula 1 pit stop decisions** using machine learning, based on the Kaggle competition:

👉 Playground Series S6E5 (Kaggle F1 Pit Stop competition)  

The objective is to **predict whether a driver will pit on the next lap**, framed as a binary classification problem and evaluated using **ROC-AUC**.

---

## 🎯 Problem Statement

Given race telemetry and contextual features such as:

- Tyre condition  
- Lap progression  
- Driver position  
- Race context  

Predict:

```

Will the driver pit in the next lap? (PitNextLap = 1 or 0)

````

---

## 🧠 Approach

This project follows a **multi-experiment iterative pipeline**, focusing on:

- Feature engineering  
- Validation strategy  
- Model optimization  

---

## 🧪 Experiments Summary

| Experiment | Description | CV AUC | LB Score |
|-----------|------------|--------|----------|
| **Exp 1** | Baseline CatBoost model | ~0.940 | ~0.940 |
| **Exp 2** | Feature engineering improvements | ↑ | ↑ |
| **Exp 3** | Hyperparameter tuning + validation refinement | ↑ | ~0.946 |
| **Exp 4** | Final optimized model | **0.948** | **0.94754** |

---

## ⚙️ Methodology

### 🔹 Model
- Gradient Boosting using **CatBoost**

### 🔹 Validation Strategy
- **GroupKFold** based on race/driver grouping  
- Prevents leakage across race sequences  

### 🔹 Feature Engineering
- Race progression indicators  
- Tyre degradation patterns  
- Interaction features (Race + Driver)  

---

## 📊 Results

- **Cross-validation AUC:** ~0.948  
- **Leaderboard Score:** 0.94754  
- **Rank:** Top ~20%  

---

## 🔍 Key Insights

- **Validation strategy > model choice**  
  Improper CV leads to misleading performance  

- **Data leakage risk via temporal/group features**  
  The `Year` feature showed strong leakage-like behavior  

- **Strong predictive signals:**
  - TyreLife  
  - RaceProgress  
  - Stint  

- **Feature interactions improved performance significantly**

---

## 📁 Project Structure

```bash
f1-pitstop-prediction/
│
├── notebooks/
│   ├── experiment1_baseline.ipynb
│   ├── experiment2_features.ipynb
│   ├── experiment3_tuning.ipynb
│   └── experiment4_final.ipynb
│
├── papers/
│   ├── exp1.pdf
│   ├── exp2.pdf
│   ├── exp3.pdf
│   └── exp4.pdf
│
├── README.md
└── requirements.txt
````

---

## 🔗 Kaggle Competition

Full competition details:
👉 [https://www.kaggle.com/competitions/playground-series-s6e5](https://www.kaggle.com/competitions/playground-series-s6e5)

---

## 📄 Citation

If you use this dataset or competition, please cite:

```bibtex
@misc{playground-series-s6e5,
    author = {Yao Yan, Walter Reade, Elizabeth Park},
    title = {Predicting F1 Pit Stops},
    year = {2026},
    howpublished = {\url{https://kaggle.com/competitions/playground-series-s6e5}},
    note = {Kaggle}
}
```

---

## 🚀 Future Work

* Model ensembling (CatBoost + LightGBM + XGBoost)
* Advanced feature interactions
* Time-series aware modeling
* Deployment as real-time prediction system

---

## 🧑‍💻 Author

**Priyanshu Lohar**

* GitHub: [https://github.com/pylhr](https://github.com/pylhr)
* LinkedIn: [https://linkedin.com/in/pylhr](https://linkedin.com/in/pylhr)
* Portfolio: [https://pylhr.vercel.app](https://pylhr.vercel.app)

---

## 💡 Final Note

```
Iterative thinking > single model performance
```

This project demonstrates how **structured experimentation + proper validation** leads to reliable machine learning systems.

```
