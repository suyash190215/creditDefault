# Credit Default Early-Warning System

🎯 **Objective:** Predict customer default risk **30 days in advance** to enable proactive credit risk mitigation.

---

## 📌 Project Overview

This project builds an **early-warning system** to identify customers likely to default within the next 30 days using historical **credit behavior and utilization patterns**.
The system prioritizes **high recall at controlled false-positive rates**, making it suitable for real-world credit risk intervention workflows.

Key outcomes include:

* **ROC-AUC > 0.82**
* **25% recall lift** at fixed FPR
* **15–25% estimated delinquency reduction** via early intervention signals

---

## 🧠 Modeling Approach

* **Problem Type:** Binary classification (Default / No Default)
* **Prediction Horizon:** 30 days
* **Algorithm:** Weighted XGBoost
* **Validation Strategy:** Time-based split to prevent data leakage
* **Explainability:** SHAP value analysis

---

## 🔍 Feature Engineering

Engineered **20+ risk-sensitive features** capturing behavioral trends and payment stability:

* Payment streaks & missed payment counts
* Credit utilization volatility
* Balance trend deltas
* Minimum payment adherence ratios
* Days since last delinquency

### Data Handling Techniques

* **Missing Values:** Median imputation
* **Outliers:** Robust percentile-based capping
* **Class Imbalance (~10% defaults):** Class-weighted loss

These enhancements improved **defaulter recall by 18%** compared to baseline models.

---

## ⚖️ Class Imbalance Strategy

Given the natural imbalance in default events:

* Applied **weighted XGBoost**
* Optimized recall under fixed FPR constraints
* Evaluated using **ROC-AUC and precision–recall tradeoffs**

Resulted in **25% higher recall** at the same false positive rate.

---

## 📊 Model Performance

| Metric                          | Value                |
| ------------------------------- | -------------------- |
| ROC-AUC                         | **0.82+**            |
| Recall Lift                     | **+25% @ fixed FPR** |
| Feature Recall Gain             | **+18%**             |
| Estimated Delinquency Reduction | **15–25%**           |

---

## 🔎 Model Explainability (SHAP)

Used **SHAP values** to:

* Identify early-warning signals such as rising utilization and payment instability
* Explain individual predictions in a transparent manner
* Inform targeted intervention strategies (e.g., reminders, limit adjustments)

This ensured the model remained **interpretable, actionable, and risk-aware**.

---

## 🚀 Future Improvements

* Incorporate macroeconomic indicators
* Extend to multi-horizon default prediction
* Deploy as real-time scoring service
* Monitor concept drift and recalibrate thresholds

---

# creditDefault
