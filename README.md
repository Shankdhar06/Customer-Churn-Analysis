# 📉 Customer Churn Analysis – E-Commerce Domain
**Author:** Vaibhav Shankdhar | **Date:** July 3, 2024

---

## 📌 Project Overview

An E-Commerce company is facing intense competition and struggling to retain existing customers. This project builds a **Customer Churn Prediction model** to identify accounts at risk of churning and provides **data-driven campaign recommendations** to reduce attrition — while keeping profitability intact.

> ⚠️ Note: In this business, **1 account can have multiple customers** — so losing one account means losing more than one customer.

---

## 🗂️ Repository Structure

| File | Description |
|---|---|
| `Customer_Churn_Capstone_Project.ipynb` | Full Python analysis notebook |
| `Customer_Churn_Data.xlsx` | Raw dataset (11,260 accounts, 19 variables) |
| `Vaibhav_Shankdhar_Capstone_Project_Customer_Churn.pdf` | Detailed project report (~28 pages) |
| `Vaibhav_Shankdhar_Capstone_Project_Customer_Churn.pptx` | Project presentation deck |
| `Problem_Statement.pdf` | Original business problem statement |

---

## 🎯 Business Objective

- Develop a **churn prediction model** for an E-Commerce company
- Identify **high-risk accounts** before they churn
- Provide **segmented, revenue-safe campaign recommendations** for potential churners

---

## 📊 Dataset Summary

- **Source:** Company account data (all accounts till date)
- **Size:** 11,260 accounts × 19 variables
- **Target Variable:** `Churn` (1 = Churned, 0 = Retained)
- **Class Distribution:** 83% Non-Churned | 17% Churned (Imbalanced)

### Key Variables
| Variable | Description |
|---|---|
| `Tenure` | Duration of the account |
| `CC_Contacted_L12m` | Customer care contacts in last 12 months |
| `rev_per_month` | Monthly average revenue |
| `rev_growth_yoy` | YoY revenue growth % |
| `Service_Score` | Customer satisfaction score on service (0–5) |
| `CC_Agent_Score` | Customer satisfaction score on CC agent (1–5) |
| `account_segment` | Account segmentation by spend (Super, HNI, Regular Plus, etc.) |
| `cashback_l12m` | Monthly average cashback |
| `Day_Since_CC_connect` | Days since last customer care contact |

---

## 🔍 Project Workflow

### 1. 🧹 Data Cleaning & Variable Transformation
- Removed special characters (`#`, `$`, `@`, `+`, `*`, `&&&&`) from multiple fields
- Standardised gender values (`F → Female`, `M → Male`)
- Fixed account segment naming inconsistencies
- Mapped all 19 variables to correct data types
- Removed **AccountID** (irrelevant for ML)
- Eliminated **308 duplicate records** → Final dataset: **10,952 rows × 18 columns**

### 2. 🔎 Missing Value Treatment
- **Continuous variables** → Imputed with **mean**
- **Categorical variables** → Imputed with **mode**
- Variables with missing values: Tenure (218), rev_per_month (791), cashback (473), Login_device (760), and others

### 3. 📈 Exploratory Data Analysis (EDA)

#### Univariate Highlights
- Tenure is **right-skewed** (skewness: 3.93) with mean ~11 months
- Revenue per month highly right-skewed (skewness: 9.33)
- Most customers gave a **service score of 3** (average satisfaction)
- ~8,000 customers login via **Mobile** vs ~3,000 via Computer
- Most payments via **Debit Card**, least via **UPI**

#### Bivariate Highlights
- **Churned accounts have lower tenure** than retained ones
- **Churned accounts contacted customer care more frequently** (lower Days_Since_CC_connect)
- **Regular Plus accounts** have the highest churn count
- Churn occurs **across all payment modes** without exception
- No significant correlation between Tenure and Revenue per month

#### Multivariate Analysis
- Heatmap shows **no major multicollinearity** among numerical variables
- Mild positive correlation between `coupon_used_for_payment` and `Day_Since_CC_connect`

### 4. 🔧 Outlier Treatment
- Used **IQR method** (Upper = Q3 + 1.5×IQR | Lower = Q1 − 1.5×IQR)
- All outliers successfully capped across numerical variables

### 5. ⚖️ Class Imbalance Analysis
- Dataset is imbalanced: **83% non-churned vs 17% churned**
- Techniques considered: Oversampling, Undersampling, **SMOTE** (preferred)

### 6. 🔵 Clustering Analysis (Hierarchical)
- Used **Ward linkage** hierarchical clustering
- **Dendrogram** identified **5 optimal clusters**
- Cluster findings:
  - Clusters 1 & 2: **High tenure accounts**
  - Clusters 3 & 5: **Medium tenure accounts**
  - Cluster 4: **Lowest tenure accounts** (highest churn risk)

---

## 💡 Key Business Insights

- Tier 1 cities have the most accounts; Tier 2 the fewest
- Accounts that churned had **lower tenure** on average
- Churned accounts had **more customers tagged** per account
- Customers who churned connected to customer care **more frequently** — indicating dissatisfaction before leaving
- UPI and E-wallet usage is very low — potential area for incentive campaigns
- Most customers are in **Regular Plus** and **Super** segments — key retention targets

---

## 🛠️ Tools & Technologies

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Wrangling-green)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange)
![Scikit-learn](https://img.shields.io/badge/ScikitLearn-ML-red)
![Scipy](https://img.shields.io/badge/Scipy-Clustering-purple)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-yellow)

- **Data Wrangling:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Clustering:** Scipy (Ward Linkage, Dendrogram)
- **Scaling:** StandardScaler (Sklearn)
- **Imbalance Handling:** SMOTE (imbalanced-learn)

---

## 🚀 How to Run

1. Clone this repository:
```bash
git clone https://github.com/Shankdhar06/customer-churn-analysis.git
```

2. Install required libraries:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy imbalanced-learn openpyxl
```

3. Open the notebook:
```bash
jupyter notebook Customer_Churn_Capstone_Project.ipynb
```

---

## 📬 Connect with Me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://www.linkedin.com/in/vaibhav-shankdhar-0602/)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-black)](https://github.com/Shankdhar06)

---
