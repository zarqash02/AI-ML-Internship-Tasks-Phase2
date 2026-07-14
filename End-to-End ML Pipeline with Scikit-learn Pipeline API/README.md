# End-to-End Machine Learning Pipeline for Customer Churn Prediction

## Overview

This project demonstrates the development of a production-ready machine learning pipeline using Scikit-learn's Pipeline API to predict customer churn. The complete workflow includes data preprocessing, model training, hyperparameter tuning, evaluation, and model export for future use.

The project emphasizes building reusable machine learning workflows by integrating preprocessing and model training into a single pipeline, making deployment and inference more reliable and consistent.

---

## Objective

The primary objective of this project is to build an end-to-end machine learning pipeline capable of predicting whether a customer is likely to churn based on their demographic and service information.

---

## Dataset

**Dataset:** Telco Customer Churn Dataset

The dataset contains customer demographics, account information, subscribed services, and a target variable indicating whether the customer has churned.

---

## Project Workflow

1. Load and inspect the dataset
2. Perform data cleaning
3. Separate features and target variable
4. Identify numerical and categorical features
5. Build preprocessing pipelines

   * Missing value imputation
   * Feature scaling
   * One-Hot Encoding
6. Create an end-to-end Scikit-learn Pipeline
7. Train multiple machine learning models
8. Perform hyperparameter tuning using GridSearchCV
9. Evaluate model performance
10. Compare models
11. Export the best-performing pipeline using Joblib
12. Load the saved pipeline and make predictions

---

## Machine Learning Models

The following classification algorithms were implemented:

* Logistic Regression
* Random Forest Classifier

---

## Data Preprocessing

The preprocessing pipeline includes:

### Numerical Features

* Median imputation for missing values
* StandardScaler for feature scaling

### Categorical Features

* Most frequent value imputation
* One-Hot Encoding

All preprocessing steps are integrated into a single `ColumnTransformer` and combined with the classifier using Scikit-learn's `Pipeline` API.

---

## Hyperparameter Tuning

Model optimization was performed using **GridSearchCV** with 5-fold cross-validation to identify the best hyperparameter combinations.

---

## Model Evaluation

The trained models were evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score
* Classification Report

The performance of Logistic Regression and Random Forest was compared to select the best-performing model.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Joblib
* Jupyter Notebook

---

## Repository Structure

```text
├── Task_2_End_to_End_ML_Pipeline.ipynb
├── Telco-Customer-Churn.csv
├── customer_churn_pipeline.pkl
└── README.md
```

---

## Learning Outcomes

Through this project, the following concepts were practiced:

* Building reusable machine learning pipelines
* Feature preprocessing using Pipeline and ColumnTransformer
* Hyperparameter tuning with GridSearchCV
* Model comparison and evaluation
* Exporting complete ML pipelines with Joblib
* Developing production-ready machine learning workflows

---

## Future Improvements

Possible enhancements include:

* Handling class imbalance using resampling techniques
* Experimenting with additional classification models such as XGBoost or LightGBM
* Building a web application for real-time churn prediction
* Deploying the trained pipeline using Flask, FastAPI, or Streamlit

---

## Author

**Zarqash Ahmed**

AI/ML Internship – Phase 2 Assignment
