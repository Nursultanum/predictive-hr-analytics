# 🧠 Predictive HR Analytics

## Employee Satisfaction and Attrition Risk Prediction

### 📌 Project Description

HR analysts at **“Careful Work”** help the business reduce financial losses associated with employee turnover. They leverage employee data and machine learning methods to **identify risks in advance** and support managerial decision-making.

This project addresses **two key HR-analytics tasks**:

1. **Predicting employee job satisfaction**
2. **Predicting employee attrition**

Job satisfaction (`job_satisfaction_rate`) is measured via surveys on a **0–1 scale**. Since surveys are costly and not always frequent, the business is interested in **predictive models** to supplement or replace manual assessments.

---

## 🎯 Research Objectives

* Identify key factors affecting:

  * employee satisfaction
  * attrition probability

* Build and compare machine learning models:

  * **Regression** — for `job_satisfaction_rate` prediction
  * **Classification** — for `quit` prediction

* Select the best models based on metrics:

  * **SMAPE** — for regression
  * **ROC-AUC** — for classification

* Provide **practical HR recommendations**.

---

## 📂 Data

Three types of datasets were used:

* **Training data:**

  * `train_job_satisfaction_rate.csv`
  * `train_quit.csv`

* **Test features:**

  * `test_features.csv`

* **Test targets:**

  * `test_target_job_satisfaction_rate.csv`
  * `test_target_quit.csv`

### Key features:

* `dept` — department
* `level` — job level (junior / middle / senior)
* `workload` — workload
* `employment_years` — tenure
* `salary` — salary
* `supervisor_evaluation` — supervisor rating
* `last_year_promo`, `last_year_violations` — HR history

---

## 🔍 Research Process

### Task 1 — Predicting Job Satisfaction

* Data cleaning and correction (`sinior → senior`)
* EDA and distribution analysis
* Correlation analysis (Spearman + Phik)
* Unified **Pipeline** with `ColumnTransformer`
* Model comparison:

  * DummyRegressor (baseline)
  * Ridge Regression
  * **Decision Tree Regressor** (best)

**Results:**

* CV SMAPE ≈ **15.1%**
* Test SMAPE ≈ **13.35%**
* Improvement over baseline ≈ **25 percentage points**

---

### Task 2 — Predicting Attrition

* Analysis of attrition factors

* Employee attrition profile creation

* Hypothesis testing: impact of satisfaction on quitting

* Addition of a new feature:

  * `job_satisfaction_pred` — prediction from Task 1

* Model comparison:

  * DummyClassifier (baseline)
  * Logistic Regression (L1)
  * KNN
  * **Decision Tree Classifier** (best)

**Results:**

* CV ROC-AUC ≈ **0.903**
* Test ROC-AUC ≈ **0.912**
* Improvement over baseline: **+0.41**

---

## 📊 Key Findings

### Satisfaction factors:

* **Supervisor evaluation** — the main driver
* **Disciplinary violations** sharply reduce satisfaction
* Salary and tenure have **indirect influence** through job level and workload

### Attrition factors:

Employees who leave are mainly:

* Junior staff

* Tenure ≤ 2 years

* Low salary

* No promotion

* Supervisor rating ≤ 3

* Job satisfaction **statistically significantly affects** attrition probability (p-value < 0.001)

---

## 🧩 Business Value

* Early identification of **risk groups**
* Supports HR decision-making
* Provides foundation for **predictive HR analytics**
* Enables shift from reactive to **proactive personnel management**

---

## 🛠 Technologies Used

* Python, pandas, NumPy
* scikit-learn
* Pipeline, ColumnTransformer
* Decision Trees, Logistic Regression, KNN
* Phik, Spearman
* Matplotlib, Seaborn

---

## 📌 Conclusion

The project demonstrates that **machine learning methods can effectively predict employee satisfaction and attrition risk**, and provide actionable recommendations to reduce turnover.
The resulting models can serve as a foundation for **intelligent HR systems** that integrate prediction, visualization, and management decision support.
