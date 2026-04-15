# 🏦 End-to-End Bank Customer Churn Analysis
 
> **Personal Project · Built for internship portfolio**
> A complete machine learning pipeline to predict and explain customer churn in retail banking — from raw data to actionable business insights.
 
---
 
## 🎯 Project Objective
 
Customer churn is one of the most expensive problems in banking. Acquiring a new customer costs 5–7× more than retaining an existing one, yet most banks still rely on reactive, rule-based alerts. This project builds a **fully end-to-end ML pipeline** that doesn't just predict *who* will churn — it explains *why*, enabling proactive retention strategies.
 
This was built as a personal project to demonstrate production-minded ML thinking: clean data pipelines, model interpretability, and business-aligned output framing.
 
---
 
## 📦 What's Inside
 
### 1. Exploratory Data Analysis (EDA)
- Distribution analysis across demographics: age, geography, tenure, balance
- Churn rate breakdown by segment — geography (France vs Germany vs Spain), gender, credit card ownership
- Correlation heatmaps to surface feature relationships
- Class imbalance identification and treatment strategy
### 2. Feature Engineering
- Derived features: balance-to-salary ratio, product density score
- Encoding of categorical variables (Geography, Gender)
- Normalisation and scaling for model compatibility
### 3. Model Training & Comparison
Multiple classifiers evaluated to find the best fit:
 
| Model | Key Strength |
|-------|-------------|
| Logistic Regression | Baseline + interpretability |
| Random Forest | Handles non-linearity, feature importance |
| XGBoost | High accuracy, handles imbalance |
| Support Vector Machine | Strong with normalised features |
 
### 4. Class Imbalance Handling
- Analysed the churn/non-churn split (typically ~20/80)
- Applied SMOTE (Synthetic Minority Over-sampling) and class weighting
- Evaluated impact on recall — the metric that matters most for churn (missing a churner is costly)
### 5. Model Evaluation
Focus on business-relevant metrics:
- **Recall** — catch as many churners as possible
- **Precision-Recall AUC** — handles imbalanced classes better than ROC-AUC
- **F1 Score** — balance between precision and recall
- Confusion matrix analysis with business cost framing
### 6. Feature Importance & Interpretability
- Random Forest feature importances
- Identification of top churn drivers: account balance, age, number of products, active membership status
- Business narrative: "A customer aged 40–60, with a single product, high balance, and low activity is your highest churn risk"
---
 
## 📊 Key Findings
 
- **Geography matters more than expected**: German customers churn at nearly 2× the rate of French customers — suggesting regional service gaps
- **Balance paradox**: High-balance customers with low product engagement are high churn risk — they have options
- **Age is a non-linear predictor**: Mid-career customers (40–55) churn more than younger or older cohorts
- **Active membership is the strongest protective factor**: Disengaged customers are 3× more likely to churn
---
 
## 🛠️ Tech Stack
 
```
Python 3.x
├── pandas, numpy          — Data wrangling
├── matplotlib, seaborn    — Visualisation
├── scikit-learn           — ML pipeline (preprocessing, models, evaluation)
├── imbalanced-learn       — SMOTE for class balancing
└── xgboost                — Gradient boosting classifier
```
 
---
 
## 📁 Repository Structure
 
```
End-to-End-Bank-CustomerChurnAnalysis/
├── Bank Customer Churn Prediction.csv   # Raw dataset (10,000 customers)
├── info.ipynb                           # Full analysis notebook (EDA → Model → Insights)
└── README.md
```
 
---
 
## 🚀 Getting Started
 
```bash
git clone https://github.com/MrinmoyBANIKYA/End-to-End-Bank-CustomerChurnAnalysis.git
cd End-to-End-Bank-CustomerChurnAnalysis
 
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn xgboost
jupyter notebook info.ipynb
```
 
---
 
## 🔭 What I'd Build Next (With Production Access)
 
If extended to a real banking environment, the natural next steps would be:
 
- **Real-time scoring API**: Deploy the trained model as a FastAPI service, scoring customers nightly based on transaction data
- **Segment-based intervention engine**: Map churn probability scores to intervention categories (low / medium / high risk) with recommended retention offers per segment
- **Drift monitoring**: Track feature distribution shifts over time to detect model degradation
- **A/B testing framework**: Measure the actual retention impact of ML-driven interventions vs. control groups
---
 
## 💼 Why This Project
 
I built this to understand the full lifecycle of an ML project in a domain where the stakes are real. Banking churn is not an academic toy problem — every percentage point of churn reduction translates to millions in retained revenue. The goal was to think like a data scientist embedded in a product team, not just a notebook coder.
 
---
 
## 👤 Author
 
**Mrinmoy Banikya** — Open to internship opportunities in data science, ML engineering, and fintech analytics.
 
---
 
## 📄 Dataset
 
Sourced from publicly available bank customer churn benchmark datasets (Kaggle). 10,000 records across 14 features including CreditScore, Geography, Gender, Age, Tenure, Balance, NumOfProducts, HasCrCard, IsActiveMember, EstimatedSalary, and Exited (target).
 