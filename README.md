# Telco Customer Churn Analysis Using Machine Learning

**Author:** Amran Thaqif Rajendra  
**Tools Used:** Python (Pandas, Scikit-learn, XGBoost, SHAP, Matplotlib, Seaborn), Excel, Tableau Public  

---

## Project Overview
This end-to-end project analyzes customer churn for a telecommunications company using **Python, Excel, and Tableau**.  
The goal is to **understand the key drivers of churn**, **predict customers at risk**, and **provide actionable business recommendations** to improve retention.

### Objectives
1. Identify main factors influencing customer churn.  
2. Predict customers most likely to churn using ML models.  
3. Compare loyal vs churned customer behavior.  
4. Translate analytical findings into business strategies.

---

## Dataset Description
The dataset is sourced from **Kaggle – Telco Customer Churn Dataset**, containing 7,043 customer records with demographic, service, and billing information.

Key columns:
- `tenure`, `Contract`, `PaymentMethod`, `InternetService`, `MonthlyCharges`, `TotalCharges`, and target variable `Churn`.

---

## Data Preparation (Python)
- Converted `TotalCharges` to numeric and handled 11 null values using median imputation.  
- Removed duplicates and trimmed whitespace.  
- Encoded categorical variables with One-Hot Encoding.  
- Applied **train-test split (80/20)** with stratification to maintain churn ratio.  

Example code snippet:
```python
df['TotalCharges'] = pd.to_numeric(df['TotalCharges'], errors='coerce')
df['Churn_binary'] = df['Churn'].map({'Yes': 1, 'No': 0})
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, stratify=y, random_state=42)
```

---

## Model Explainability (SHAP)
![SHAP Result](images/SHAP_Result.png)

## Exploratory Data Analysis
![Pairplot](images/pairplot_relationships.png)

## Business Analysis (Excel)
![Churn by Contract Type](images/pivot_contract_churn.png)
![Churn by Payment Method](images/pivot_payment_churn.png)
![Loyalty Segmentation](images/pivot_loyalty_churn.png)

## Tableau Dashboards
### Dashboard 1 – Overview
![Dashboard Overview](images/tableau/Dashboard_OverallOverview.png)

### Dashboard 2 – Customer Behaviour
![Customer Behaviour Dashboard](images/tableau/Dashboard_CustomerBehaviour.png)

