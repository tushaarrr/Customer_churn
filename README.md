# 💳 CardPulse — Credit Card Customer Churn Analysis

![Python](https://img.shields.io/badge/Python-3.9-blue) ![MySQL](https://img.shields.io/badge/MySQL-8.0-orange) ![Tableau](https://img.shields.io/badge/Tableau-Public-lightblue) ![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-green) ![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

> Predicting and analyzing credit card customer churn across 25,000 customers using a full analytics pipeline — from SQL attrition analysis to machine learning classification and Tableau dashboards.

---

## 📌 Problem Statement

Credit card companies face a critical challenge: identifying customers likely to churn before they leave. This project analyzes **25,000 credit card customer records** to uncover behavioral and financial signals that drive attrition, and builds a classification model to predict churn risk.

---

## 🗂️ Project Structure

| File | Description |
|---|---|
| `EDA.ipynb` | Data cleaning, outlier handling (IQR), SMOTE balancing, feature engineering, 20+ visualizations |
| `Credit_Card_Customers_Segmentation.ipynb` | Customer segmentation and credit score analysis |
| `Bank_Credit_Card_Churn_Prediction.ipynb` | 11 ML models trained, evaluated, and compared |
| `Credit_Card_SQL_Analysis.txt` | 6 SQL queries for attrition analysis across geographies |
| `Tableau_Workbook.twbx` | Interactive Tableau dashboard *(coming soon)* |
| `CreditCard.csv` | Raw dataset (25,000 rows, 24 features) |
| `CreditCard_cleaned_balanced.csv` | Cleaned and SMOTE-balanced dataset for ML training |

---

## ⚙️ Pipeline

```
Raw CSV → Data Cleaning → Feature Engineering → EDA → SQL Analysis → ML Modeling → Tableau Dashboard
```

**1. Data Cleaning** — Corrected typos (Geramany → Germany), standardized `Payment_of_Min_Amount` (NM → No), dropped redundant `Credit_Score` column, capped outliers using IQR method

**2. Feature Engineering** — Transformed `Type_of_Loan` into 12 binary columns (Has_Auto_Loan, Has_Personal_Loan etc.), created `Debt_to_Income_Ratio`, `Credit_History_Years`

**3. Class Imbalance** — Applied **SMOTEENN** (SMOTE + Edited Nearest Neighbours) to balance attrited vs existing customer classes for model training

**4. EDA** — 20+ visualizations revealing churn patterns across geography, occupation, credit score, payment behaviour, and income

**5. SQL** — 6 attrition queries including age-range bucketing, gender breakdown, payment status analysis

**6. ML** — 11 classification models trained and compared on balanced dataset

**7. Tableau** — Interactive dashboard with churn KPIs, geographic breakdown, and financial risk profiling

---

## 📊 Exploratory Data Analysis

### Age Distribution by Status
![Age by Status](boxplot_age_vs_status.png)

### Annual Income by Status (Box Plot)
![Annual Income Box](boxplot_annual_income_vs_status.png)

### Annual Income by Status (Violin)
![Annual Income Violin](violin_annual_income_status.png)

### Gender Distribution by Status
![Gender](gender_vs_status_countplot.png)

### Payment of Min Amount by Status
![Payment](payment_of_min_amount_vs_status_countplot.png)

### Outstanding Debt vs Credit Utilization Ratio
![Scatter](scatter_outstanding_debt_credit_utilization_ratio.png)

### Distribution of Outstanding Debt
![Outstanding Debt](hist_outstanding_debt.png)

### Distribution of Credit Utilization Ratio
![Credit Utilization](hist_credit_utilization_ratio.png)

### Distribution of Number of Credit Cards
![Num Credit Cards](hist_num_credit_card.png)

### Correlation Heatmap
![Heatmap](correlation_heatmap.png)

---

## 🤖 Machine Learning Results

**Target Variable:** `Status` (Attrited = 1, Existed = 0) — Binary Classification

**Features:** Age, Annual Income, Credit Score, Credit Utilization Ratio, Outstanding Debt, Delay from Due Date, Num of Loans, Payment of Min Amount, Geography, Occupation, Gender, 12 Loan type binary flags

| Model | Accuracy |
|---|---|
| Random Forest Classifier | — |
| Extra Trees Classifier | — |
| AdaBoost Classifier | — |
| Bagging Classifier | — |
| Decision Tree Classifier | — |
| Logistic Regression | — |
| KNN | — |
| SVM | — |
| Gaussian / Multinomial / Bernoulli Naive Bayes | — |

> **Imbalance Handling:** SMOTEENN applied before model training to improve Recall on minority (Attrited) class

---

## 🛢️ SQL Analysis

6 queries written against the raw dataset:

- **Overview** — First 10 entries for data inspection
- **Geographic distribution** — Customer count by country
- **Occupation breakdown** — Top 5 occupations among existing customers
- **Age-range bucketing** — Attrited customers split into 0-20, 20-40, 40-60, 60+ bands
- **Gender split** — Male vs Female across Attrited and Existed
- **Payment status** — Attrited customers by min payment compliance

---

## 📈 Tableau Dashboard *(coming soon)*

Three interactive dashboard views:

**Dashboard 1 — Churn Overview** — Churn rate KPI by geography, gender and occupation breakdown, credit score by status

**Dashboard 2 — Financial Risk Profile** — Debt-to-Income ratio by churn, credit utilization vs monthly balance, outstanding debt vs churn rate

**Dashboard 3 — Behavioral Signals** — Delayed payments vs churn, loan type vs attrition, credit history length vs churn risk

---

## 🔍 Key Insights

- 💳 Interest rates **above 15%** correlate with significantly worse credit scores
- 🏦 Holding **more than 5 bank accounts** negatively impacts credit scores
- ⏰ Delaying payments **more than 17 days** hurts credit scores
- 💰 Outstanding debt **above $1,338** correlates with poor credit scores
- 📅 Longer credit history consistently leads to better credit scores
- 🔁 Taking **more than 3 loans simultaneously** negatively impacts credit scores
- 👫 Gender shows **no significant difference** in churn rate
- 💵 Annual income distribution is **nearly identical** between Attrited and Existed customers

---

## 🧰 Tech Stack

| Tool | Purpose |
|---|---|
| Python (Pandas, NumPy) | Data cleaning & feature engineering |
| Matplotlib, Seaborn | EDA visualizations |
| Scikit-learn | 11 ML models, evaluation |
| imbalanced-learn (SMOTEENN) | Class imbalance handling |
| MySQL | SQL attrition analysis |
| Tableau Public | Interactive dashboards |

---

## 📁 Dataset

- **25,000** credit card customer records | **24** original features
- Geographies: India, France, Spain, Germany
- Target: `Status` (Attrited / Existed)
