Aquí tienes el README mejorado combinando ambos:
markdown# 🏥 Hospital Readmission Prediction — Diabetes Patients
## Machine Learning for Healthcare Risk Stratification

## 📌 Overview

Hospital readmissions are a major challenge in healthcare systems, 
leading to increased costs and reduced quality of care.

This project develops a machine learning model to predict **30-day 
hospital readmission risk** in diabetic patients, combining exploratory 
data analysis with predictive modeling to identify high-risk profiles.

The goal is to transform clinical data into **actionable insights** 
that can support early intervention and better resource allocation.

---

## 🎯 Objective

To identify patients at high risk of hospital readmission and support 
decision-making processes that improve patient outcomes and reduce 
healthcare costs.

---

## 🏥 Business Context

Hospital readmissions represent:
- 💸 Significant financial burden for healthcare systems
- ⚠️ Indicator of gaps in patient management
- 📉 Reduced operational efficiency

👉 A predictive model can help:
- Prioritize high-risk patients before discharge
- Optimize follow-up care and resource allocation
- Reduce penalties from CMS (Centers for Medicare & Medicaid Services)
- Improve patient outcomes through targeted interventions

---

## 📊 Dataset

- **Source:** Diabetes 130-US Hospitals Dataset (UCI ML Repository)
- **Size:** 101,766 encounters → 35,394 after cleaning
- **Period:** 1999-2008, 130 US hospitals
- **Variables:** 50 clinical and administrative features
- **Target:** Readmission within 30 days (**8.7% prevalence**)

---

## 🏗️ Pipeline

1. **Data Cleaning** — deduplication, missing values, invalid records
2. **Feature Engineering** — age recoding, medication simplification
3. **Exploratory Analysis** — readmission patterns by age, LOS, diagnoses
4. **Model Training** — Random Forest with 5-fold CV and SMOTE
5. **Threshold Tuning** — optimized for clinical screening (threshold = 0.10)
6. **Variable Importance** — key clinical predictors identified

---

## 📈 Results

| Metric | Value |
|---|---|
| ROC-AUC | 0.627 |
| PR-AUC | 0.140 (vs baseline 0.087) |
| Sensitivity (threshold=0.10) | ~75% |

👉 ROC-AUC of 0.627 is **consistent with published literature** 
(typical range: 0.60-0.70 for readmission prediction).

---

## 🔑 Key Predictors

| Predictor | Clinical Interpretation |
|---|---|
| **Gender** | Different readmission patterns in male/female diabetic patients |
| **Insulin** | Glycemic instability indicator during hospitalization |
| **Medication change** | Undertreated patients at higher discharge risk |

---

## 💥 Clinical and Business Impact

With ~35,000 diabetic patients in this dataset:
- The model identifies **~75% of high-risk patients** at threshold 0.10
- This represents ~**2,300 patients** who could receive targeted interventions
- A **10% reduction in readmissions** would translate into significant 
cost savings and improved patient outcomes

---

## 🧠 Key Insights

- Predicting readmission is genuinely difficult — moderate AUC reflects 
real clinical complexity, not model failure
- Threshold tuning is essential — default 0.5 threshold detects zero cases
- PR-AUC is more informative than accuracy for rare clinical events
- Real hospital data requires extensive cleaning before any analysis
- Feature importance provides clinically actionable insights

---

## ⚠️ Limitations

- Moderate predictive performance limits immediate clinical utility
- Missing social determinants of health and HbA1c trajectories
- No external validation dataset

---

## 🚀 Future Work

- Incorporate additional clinical variables (HbA1c, social support)
- Explore XGBoost and LightGBM
- Apply cost-sensitive learning with explicit readmission costs
- Develop clinical decision support Shiny dashboard
- Validate on independent hospital dataset

---

## 🛠️ Tech Stack

- R 4.5.3
- `caret`, `randomForest`, `themis`, `pROC`
- `precrec`, `MLmetrics`, `vip`, `tidyverse`

## 📁 Files

- `hospital_readmission.Rmd` — R Markdown source code
- `hospital_readmission.html` — Full rendered report

---

## 💼 Why This Project Matters

✔ Real-world messy clinical data (101,766 records)
✔ Clinically and financially meaningful problem
✔ Honest reporting of moderate performance with context
✔ Appropriate metrics for rare clinical events
✔ Actionable clinical and business recommendations
✔ Bridges gap between data science and healthcare decision-making

---

## 👩‍💻 Author

**Noelia Caba Martin**
Junior Data Analyst / Biostatistician
Interested in health data, bioinformatics and applied machine learning

⭐ Feel free to star the repo or connect!
