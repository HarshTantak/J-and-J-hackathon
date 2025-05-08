
# CodeSyrup - Predicting Early Readmission Risk in Diabetic Patients

**CodeSyrup** is a data science and machine learning project developed as part of **Hack-A-Stat 2025** to analyze hospital readmission risks in diabetic patients. Using clinical data from over 130 US hospitals spanning ten years, the project builds predictive models to identify patients at high risk of early readmission (within 30 days). The goal is to enable healthcare providers to take preventive actions, reduce healthcare costs, and improve patient outcomes.

---

## 💡 Problem Statement

Hospital readmissions, especially within 30 days, are a critical measure of healthcare quality. Diabetic patients face frequent complications, making them highly susceptible to readmission. This project analyzes ten years of diabetic patient data to:

- Identify key factors influencing early readmissions.
- Develop predictive models to forecast high-risk cases.
- Provide actionable insights for better diabetes management.

---

## 📊 Dataset

- Source: Clinical data from 130 US hospitals (1999–2008)
- Patients: Diagnosed with diabetes and stayed ≤14 days
- Records: ~70,000 encounters
- Key features:
  - **Demographics**: Age, gender, race
  - **Clinical**: Number of diagnoses, time in hospital, A1C results
  - **Medications**: Metformin, insulin, medication changes
  - **Outcomes**: Readmission status (`<30`, `>30`, `No`)

---

## ⚙️ Methodology

### 🔍 Data Preprocessing

- Removed `weight` column due to >95% missing values.
- Imputed `A1Cresult` with mode.
- Handled unknown `medical_specialty` entries separately.
- Recategorized target `readmitted` as:
  - **1**: Readmission within 30 days (`<30`)
  - **0**: No or late readmission (`>30` or `No`)
- Encoded categorical variables (label and one-hot encoding).

---

### 📈 Exploratory Data Analysis (EDA)

- **Time in Hospital**: Right-skewed; most stays are short.
- **Age vs Readmission**: Older patients more likely to be readmitted.
- **HbA1c and Medication Changes**: Higher HbA1c linked to increased medication adjustments.
- **Demographic Insights**: Caucasian males had the highest readmission rates.

---

### 🤖 Models Used

| Model             | Accuracy | Notes                                 |
|------------------|----------|----------------------------------------|
| Logistic Regression | 75%      | Selected for binary classification and interpretability |
| Random Forest     | 75%      | Higher complexity, same accuracy       |
| K-Nearest Neighbors | Moderate | Struggled with imbalanced data        |

- **Logistic Regression** was chosen due to its simplicity and effectiveness for binary outcomes.

---

### 🔬 Multicollinearity Analysis

- Correlation matrix showed no significant multicollinearity (no features > 0.7 correlation).
- PCA was considered but deemed unnecessary.

---

### ✅ Model Validation

- **ROC AUC**: 0.65 — better than random, room for improvement.
- **Precision-Recall AUC**: 0.10 — model struggles with minority class.
- **Confusion Matrix**:
  - True Negatives: 13,189
  - False Positives: 2
  - False Negatives: 639
  - True Positives: 4
- Imbalance remains a challenge; future versions may include SMOTE or cost-sensitive learning.

---

## 🧠 Key Insights

- **HbA1c Levels** are strongly linked to early readmissions and medication changes.
- **Medication adjustments** (metformin/insulin) increase as A1C levels rise.
- **Longer hospital stays** and more diagnoses correlate with higher readmission risks.

---

## 📌 Recommendations

- Use model outputs to flag high-risk diabetic patients before discharge.
- Monitor HbA1c trends and adjust medications accordingly.
- Improve data balance for future models via oversampling or better class weighting.

---

## 📁 Repository

GitHub: [https://github.com/HarshTantak/J-and-J-hackathon](https://github.com/HarshTantak/J-and-J-hackathon)

---

## 👥 Team

- Aarshi Shaikh  
- Prashant Srivastava  
- Harsh Tantak  

Team Name: **Code Syrup**

---

## 📜 License

This project is intended for academic and research use. Please cite appropriately if used in derivative works.
