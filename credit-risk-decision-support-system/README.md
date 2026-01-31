# Credit Risk Decision Support System for Energy Project Financing

## Overview
This project presents a credit risk decision support system designed to assist financial institutions in evaluating financing applications, particularly within energy and infrastructure-related contexts. The system leverages interpretable machine learning to estimate credit risk and translate predictive outputs into standardized risk scores and actionable financing decisions.

Rather than producing a binary approval or rejection outcome, the model focuses on decision support by enhancing transparency, governance alignment, and risk visibility.

---

## Business Problem
Financing large-scale energy and infrastructure projects involves significant credit risk, where delayed repayments or project failure may result in substantial financial losses. Traditional credit assessment approaches often rely on manual judgment or rigid rules, limiting their ability to capture complex risk patterns in applicant data.

This project aims to support risk-aware financing decisions through data-driven modeling while maintaining interpretability and regulatory suitability.

---

## Objectives
- Estimate the probability of rejection as a proxy for credit risk  
- Convert model outputs into standardized risk scores (0–100)  
- Define transparent decision rules (Approve / Conditional Approval / Reject)  
- Support governance, consistency, and explainable decision-making  

---

## Dataset
The dataset consists of historical financing applications, where:
- Each record represents a financing request
- The target variable (`Loan_Status`) indicates approval (1) or rejection (0)
- Approval/rejection is treated as a proxy for credit risk assessment

Missing values are handled using:
- Median imputation for numerical variables
- Mode imputation for categorical variables  
(Test data imputation is based on training statistics to prevent data leakage.)

---

## Feature Engineering
Key engineered features include:
- **Total Income**: Combined applicant and co-applicant income  
- **Loan-to-Income Ratio**: Measures repayment capacity  
- **Credit History Flag**: Indicates prior good credit behavior  
- **Graduate & Self-Employed Indicators**: Risk-related applicant attributes  

Categorical variables are encoded using one-hot encoding with alignment between training and test sets.

---

## Model Selection
**Logistic Regression** was selected due to its high interpretability, which is critical in credit risk and decision support systems. The project prioritizes transparency, explainability, and governance alignment over purely maximizing predictive accuracy.

---

## Model Evaluation
The model is evaluated using:
- Confusion Matrix  
- Classification Report  
- ROC-AUC Score  

Given the moderate class imbalance (~69% approvals vs 31% rejections), ROC-AUC is emphasized to ensure balanced performance beyond simple accuracy.

---

## Risk Scoring & Decision Layer
The model outputs the **probability of rejection**, which is treated as a proxy for credit risk. This probability is converted into a standardized **Risk Score (0–100)** and mapped to financing decisions using predefined thresholds:

- **Approve – Low Risk**  
- **Conditional Approval**  
- **Reject – High Risk**  

This decision layer transforms predictive insights into actionable recommendations.

---

## Test Deployment Simulation
The trained model is applied to unseen test data to simulate real-world deployment. Final outputs include:
- Probability of Rejection  
- Risk Score  
- Financing Decision  

Results are exported as a CSV file for operational use.

---

## What-If Analysis
Scenario-based analysis is conducted to assess risk sensitivity:
- Increasing loan amount by 20%  
- Improving applicant income by 15%  

This analysis helps decision-makers understand how financial changes impact credit risk.

---

## Limitations & Future Enhancements
- Benchmarking against tree-based models (e.g., Random Forest, XGBoost)  
- Exploring class imbalance handling techniques (resampling, class weighting)  
- Optimizing decision thresholds based on institutional risk appetite  

---

## Technologies Used
- Python  
- Pandas, NumPy, Matplotlib  
- Scikit-learn  
- Jupyter Notebook / Google Colab  

---

## Author
**Duaa Barnawi**  
Artificial Intelligence & Data Analytics Graduate  
Focus: Risk Analytics & Decision Support Systems  

LinkedIn: https://www.linkedin.com/in/duaa-barnawi-898b02302
