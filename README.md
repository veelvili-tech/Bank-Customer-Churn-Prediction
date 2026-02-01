# Project Background

Customer churn is a critical business challenge in the banking industry, where acquiring new customers is significantly more expensive than retaining existing ones. This project was developed from the perspective of a **data scientist working at a multinational retail bank**, with the goal of leveraging historical customer data **to predict churn risk and support proactive retention strategies.**

The bank operates across multiple geographic regions and offers a range of financial products, including savings accounts, credit services, and premium banking tiers. Key business metrics impacted by churn include customer lifetime value (CLV), profitability, cross-sell opportunities, and marketing acquisition costs.

As customer behavior becomes increasingly data-driven, this project demonstrates how **machine learning models can be operationalized to support business decisions,** enabling marketing, customer relationship, and executive teams to intervene before high-value customers leave.

# Business Questions Addressed

Insights and model-driven recommendations are provided across the following key areas:

- 1. Customer Churn Drivers
Which behavioral and demographic factors are most strongly associated with churn?

- 2. Predictive Modeling Performance
Which machine learning models are most effective at identifying at-risk customers?

- 3. Model Interpretability & Feature Importance
Which variables have the greatest influence on churn predictions?

- 4. Deployment & Business Readiness
How can churn predictions be delivered to stakeholders in a usable, secure way?


# Data Structure & Initial Checks

The dataset represents anonymized customer-level records from a multinational bank and includes:

- Demographic attributes (e.g., age, gender, geography)
- Account information (e.g., balance, number of products, credit score)
- Behavioral indicators (e.g., activity status, complaints, satisfaction score)
- Target variable: Exited (customer churn)

Key preprocessing steps included:

- Removal of non-predictive identifiers
- Handling class imbalance using SMOTE
- Outlier treatment using IQR, winsorization, and Z-score methods
- Feature encoding (label, ordinal, and one-hot encoding)
- These steps ensured the data was model-ready, balanced, and reproducible.

# Executive Summary
Overview of Findings

From a business perspective, three key insights stand out:

- Customer complaints are the strongest predictor of churn, significantly outweighing demographic and financial features.
- Tree-based ensemble models (Random Forest and XGBoost) dramatically outperform linear and distance-based models in identifying churn risk.
- A locally deployed ML application can effectively translate model predictions into actionable insights for non-technical stakeholders.

These findings enable the bank to shift from reactive churn management to proactive, data-driven retention strategies.


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

### Feature Importance & Interpretability
Top predictive features included:

- Complain
- Age
- Number of Products
- Activity Status
- Geographic Indicators

By narrowing the feature set to the most influential variables, the model remains both **accurate and explainable**, which is critical for stakeholder trust and regulatory environments.

### Deployment & Decision Support
The final Random Forest model was deployed using Streamlit as a local web application, allowing users to:

- Input customer attributes
- Receive real-time churn probability predictions
- Support decision-making without requiring ML expertise

This deployment approach demonstrates how machine learning models can be **bridged into business workflows**, not just evaluated offline.

### Recommendations

Based on the findings, the following actions are recommended for stakeholder teams:

- Customer Experience Teams:
Prioritize complaint resolution and proactive outreach for customers with recent negative interactions.

- Marketing & Retention Teams:
Use churn predictions to design targeted retention campaigns for high-risk customer segments.

- Product Strategy Teams:
Review product bundling strategies, as customers with fewer products are more likely to churn.

- Data & Analytics Teams:
Integrate churn predictions into CRM systems to enable continuous monitoring and intervention.

# Assumptions & Caveats

- The dataset is anonymized and may not capture all real-world behavioral signals.
- Churn is treated as a binary outcome, without modeling time-to-churn.
- Local deployment is intended for prototyping and demonstration, not production-scale usage.
