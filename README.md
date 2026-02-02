# Project Background

Customer retention is a critical business priority in the banking industry, where acquiring a new customer can cost **5–7x** more than retaining an existing one. This project focuses on building a machine learning–driven churn prediction system that helps a retail bank proactively identify customers at risk of leaving and take targeted, cost-effective retention actions.

This project **simulates the work of a data science team within a retail banking organization**, operating in a competitive environment shaped by fintech disruption and rising customer expectations. The objective is to translate customer data into actionable insights that support strategic decision-making across marketing, customer relationship management, and revenue protection teams.

Acting as a **data analyst / data scientist embedded within the business**, my role was to design and deliver an **end-to-end churn modeling pipeline**, covering data exploration, preprocessing, feature engineering, model development, evaluation, and the formulation of **business-oriented recommendations**. The project emphasizes not only predictive performance, but also interpretability and real-world applicability, ensuring the model can be realistically adopted in a production banking environmen

**The Python scripts for EDA and data cleaning can be found here [[link](https://github.com/veelvili-tech/Bank-Customer-Churn-Prediction/tree/main/Part%201_EDA)], and the scripts for model building can be found here [[link](https://github.com/veelvili-tech/Bank-Customer-Churn-Prediction/blob/main/Part%202_Final_Model_Building.ipynb)].**

# Business Background

The bank operates in the retail banking sector, offering products such as savings accounts, credit cards, personal loans, and digital banking services. With increasing competition from fintech players and digital-first banks, customer churn directly impacts:

- Revenue stability
- Customer lifetime value (CLV)
- Marketing and retention costs

The objective of this project is to predict churn before it happens, enabling the bank to move from reactive retention to proactive, data-driven decision making.

# Business Objective

- Identify customers with a high probability of churn
- Understand key drivers behind churn behavior
- Recommend actionable retention strategies aligned with business priorities

# Data Structure & Initial Checks

The dataset consists of customer-level banking information, including:

- Demographics: age, gender, geography
- Account information: tenure, balance, number of products
- Engagement metrics: credit card ownership, active membership
- Target variable: customer churn (Yes / No)

**Initial checks included:**

- Missing value analysis
- Duplicate record checks
- Target class imbalance assessment

# Data Preprocessing & Feature Engineering

Key preprocessing steps:

- Encoding categorical variables (e.g., geography, gender)
- Feature scaling for algorithms sensitive to magnitude
- Handling class imbalance using SMOTE
- Train-test split (80/20) to ensure reliable evaluation

**Exploratory Data Analysis (EDA) highlighted strong churn signals such as:**

- Low tenure
- Inactive membership
- Fewer banking products
- Low account engagement despite high balances

# Model Development

Multiple supervised machine learning models were developed and compared:

- Logistic Regression – baseline, high interpretability
- Random Forest – robust ensemble model with feature importance
- XGBoost – high predictive power with optimized performance

All models were trained using the same dataset and evaluated consistently.

# Model Evaluation & Performance

Models were evaluated using business-relevant metrics:

- Accuracy
- Precision
- Recall (critical to minimize missed churners)
- F1-Score
- Cross-validation stability

Key outcome:
Random Forest delivered the best balance between performance, stability, and interpretability, making it the preferred model for deployment.

# Model Insights (What Drives Churn?)

Top churn drivers identified:

- Inactive customer status
- Low product penetration (1 or fewer products)
- Short customer tenure
- High balance with low engagement (potential dissatisfaction)

These insights provide clear levers for business intervention, not just predictions.

# Executive Summary (Key Findings)
If a business stakeholder were to take away three key insights, they would be:

- Customer engagement matters more than balance — high-balance but inactive customers are at high churn risk.
- Early-stage customers are fragile — churn likelihood is highest in the first few years.
- ML-driven targeting can optimize retention spend, focusing offers only on high-risk customers instead of blanket campaigns.

# Insights Deep Dive
### 1. Churn Drivers & Customer Behavior

- Customers who filed complaints showed a substantially higher likelihood of churn, making complaint history the most critical early warning signal.
- Older customers exhibited higher churn probability, suggesting lifecycle-based engagement gaps.
- Active customers were significantly less likely to churn, highlighting the value of engagement initiatives.

Business implication: Complaint resolution speed and customer engagement programs are high-impact levers for retention.

### 2. Model Performance Comparison

Six classification models were evaluated:

- Logistic Regression
- K-Nearest Neighbors
- Support Vector Machine
- Naive Bayes
- Random Forest
- XGBoost

**Key results:**

- Random Forest and XGBoost achieved ~99.9% accuracy, with near-perfect precision and recall.
- Simpler models struggled to correctly identify churners, leading to high false negatives.
- Random Forest was selected as the final model due to its slightly superior recall and interpretability.

**Business implication:** Choosing the right model directly affects how many at-risk customers are correctly identified before churn occurs.

### 3. Feature Importance & Interpretability
Top predictive features included:

- Complain
- Age
- Number of Products
- Activity Status
- Geographic Indicators

By narrowing the feature set to the most influential variables, the model remains both **accurate and explainable**, which is critical for stakeholder trust and regulatory environments.

### 4. Deployment & Decision Support
The final Random Forest model was deployed using Streamlit as a local web application, allowing users to:

- Input customer attributes
- Receive real-time churn probability predictions
- Support decision-making without requiring ML expertise

This deployment approach demonstrates how machine learning models can be **bridged into business workflows**, not just evaluated offline.

# Business Recommendations
Based on the analysis, the bank should consider:

- Targeted retention campaigns for high-risk customers instead of mass offers
- Proactive outreach to inactive customers with high balances
- Cross-selling strategies to increase product adoption early in the customer lifecycle
- Integrating the churn model into CRM systems for real-time risk scoring

# Assumptions & Caveats

- The dataset is anonymized and may not capture all real-world behavioral signals.
- Churn is treated as a binary outcome, without modeling time-to-churn.
- Local deployment is intended for prototyping and demonstration, not production-scale usage.

# Deployment 

The application was developed using Streamlit and a Random Forest model, aiming to provide
predictive insights into customer churn.

![bf947998-8ba1-4542-93b8-f596cc10c153](https://github.com/user-attachments/assets/8f5ff815-3f3a-4a03-896b-d946dd3d43b2)

### Deployment Process
The deployment process on a local host involves the following steps:

### a. Setting Up the Environment
1. Install Python 3.10 or higher.
2. Create a virtual environment and activate it.
3. Install the required dependencies: pip install -r requirements.txt

### b. Running the Application
1. Navigate to the directory containing the application code.
2. Start the Streamlit application by running: streamlit run app.py [[link](https://github.com/veelvili-tech/Bank-Customer-Churn-Prediction/tree/main/APP)]
3. Open the provided URL (e.g., http://localhost:8501) in a browser to interact with the
application.

