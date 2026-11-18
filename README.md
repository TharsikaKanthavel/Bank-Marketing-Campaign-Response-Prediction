# 🏦 Bank Marketing Campaign Response Prediction

A Machine Learning project that predicts whether a customer will subscribe to a term deposit based on demographic, financial, and previous marketing campaign information. The project develops an end-to-end machine learning pipeline using the UCI Bank Marketing dataset and compares multiple classification models to improve marketing campaign effectiveness.

---

## 📌 Project Overview

Marketing campaigns often contact thousands of customers, but only a small percentage subscribe to a term deposit. Accurately identifying potential subscribers allows banks to reduce marketing costs while increasing campaign efficiency.

This project builds and evaluates multiple machine learning models to predict customer responses and proposes a customer prioritization strategy to support targeted marketing decisions.

---

## 🎯 Objectives

- Predict customer term deposit subscriptions.
- Perform comprehensive data preprocessing and feature engineering.
- Compare multiple machine learning classification models.
- Optimize model performance using validation-based threshold tuning.
- Develop customer prioritization tiers for marketing campaigns.

---

## 📂 Dataset

**Dataset:** UCI Bank Marketing Dataset

- Source: UCI Machine Learning Repository
- Marketing campaign data collected from a Portuguese banking institution
- Binary Classification:
  - **Yes** → Customer subscribed to a term deposit
  - **No** → Customer did not subscribe

---

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Matplotlib
- Seaborn
- Machine Learning
- Feature Engineering
- Statistical Analysis
- Jupyter Notebook

---

## ⚙️ Project Workflow

### 1. Data Preprocessing

- Missing value handling
- Duplicate removal
- Feature engineering
- Categorical encoding
- Numerical feature scaling
- Stratified dataset splitting (60% Train, 20% Validation, 20% Test)

---

### 2. Exploratory Data Analysis (EDA)

Performed detailed exploratory analysis to understand customer characteristics and campaign performance.

Visualizations include:

- Target distribution
- Age distribution
- Job category analysis
- Marital status analysis
- Education level
- Previous campaign outcomes
- Correlation heatmaps
- Feature distributions

---

### 3. Feature Engineering

- Created derived features
- Processed categorical variables
- Standardized numerical variables
- Removed redundant attributes
- Prepared data for machine learning models

---

## 🤖 Machine Learning Models

The following classification models were trained and evaluated:

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Random Forest
- Gradient Boosting
- XGBoost

---

## 📊 Model Evaluation

Models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC
- Confusion Matrix
- ROC Curve

---

## 🏆 Results

| Model | Performance |
|--------|-------------|
| Logistic Regression | Baseline Model |
| K-Nearest Neighbors | Evaluated |
| Random Forest | Evaluated |
| Gradient Boosting | **Best Model** |
| XGBoost | Evaluated |

### Best Model

✅ **Gradient Boosting**

- **Test ROC-AUC:** **0.8153**
- Excellent balance between precision and recall.
- Strong generalization performance on unseen data.

---

## 🎯 Customer Prioritization Strategy

To support marketing decision-making, customers were categorized into probability-based priority groups:

- 🟢 High Priority
- 🟡 Medium Priority
- 🔴 Low Priority

This enables marketing teams to focus resources on customers with the highest likelihood of subscribing, improving campaign efficiency and reducing unnecessary outreach.

---

## 📈 Business Impact

The developed solution can help banks:

- Improve marketing campaign targeting.
- Increase term deposit subscription rates.
- Reduce campaign costs.
- Prioritize high-value customers.
- Support data-driven marketing decisions.

---

## 📚 Learning Outcomes

This project strengthened my practical skills in:

- End-to-End Machine Learning
- Data Preprocessing
- Exploratory Data Analysis (EDA)
- Feature Engineering
- Model Training
- Hyperparameter Evaluation
- Model Comparison
- ROC-AUC Analysis
- Classification Performance Evaluation
- Predictive Analytics
- Business Decision Support

---

## 🚀 Future Enhancements

- Hyperparameter optimization using Grid Search or Bayesian Optimization.
- Explainable AI using SHAP or LIME.
- Deploy the model as a web application using Flask or FastAPI.
- Integrate real-time prediction APIs.
- Develop an interactive Power BI dashboard for campaign monitoring.

---



BSc (Hons) Information Technology – Data Science  
Sri Lanka Institute of Information Technology (SLIIT)

GitHub: https://github.com/TharsikaKanthavel
