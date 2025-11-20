# SaaS Churn Analytics
End-to-end SQL + Python project analyzing churn, cohorts and revenue drivers for a fictional SaaS company.

### Overview
This project simulates the analytical workflow of a Data Analyst working in a SaaS environment.  
The goal is to understand customer churn, cohort behavior and revenue trends through a full data pipeline:

- SQL for feature engineering and metric generation  
- Python for data validation, EDA and modeling  
- Business interpretation to identify insights that support decision-making  

The structure and methodology reflect real analytical work performed in consulting and data-driven companies.

### Business Objectives
A fictional SaaS company wants to understand
- Why are customers churning?  
- Which features predict churn?  
- How do customer cohorts behave over time?  
- What business actions could reduce churn and increase revenue?  
- What is the financial impact of churn?  
The final deliverable includes metrics, dashboards (coming soon), insights, and a predictive model.

## Dataset & Sources
This project uses synthetic SaaS data designed to replicate real subscription businesses.  
Main tables include:

- customers: customer info, acquisition date, segment  
- subscriptions: plan type, monthly revenue, start/end dates  
- activity_logs: product usage metrics  
- support_tickets: interactions with customer support  
- payments: invoices and payment status

All datasets are structured to allow:
- Cohort analysis  
- LTV estimation  
- Churn prediction  
- Revenue trend exploration

## Project Structure

```
project/
├── data/
│   ├── raw/
│   └── processed/
├── sql/
│   ├── cohorts.sql
│   ├── churn_features.sql
│   └── revenue_metrics.sql
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_feature_engineering.ipynb
│   └── 03_churn_model.ipynb
├── src/
│   ├── utils.py
│   ├── preprocessing.py
│   └── modeling.py
├── README.md
└── requirements.txt
```


## Languages & tools
- Python (Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn)  
- SQL (PostgreSQL / SQLite)  
- Power BI (dashboard coming soon)  
- Git & GitHub

## Methodology (Pipeline) 
1. Data loading & cleaning 
2. SQL feature engineering  
3. EDA in Python
4. Cohort analysis  
5. Customer churn segmentation  
6. Predictive modeling (logistic regression / tree-based models)
7. Business insight extraction
8. Dashboard & reporting (Power BI)

