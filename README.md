# Project Overview 

In this project, we aim to build a predictive model to determine whether an individual will default on a loan. This is a classification problem based on a dataset obtained from **Kaggle**.

## Goal of the Project
The primary objective is to develop a machine learning model that can accurately predict loan default, helping financial institutions minimize risk and improve lending strategies.

## Business Impact
- **Better Risk Management**  
  Helps lenders assess the creditworthiness of applicants, reducing the likelihood of bad loans.
  
- **Optimized Loan Approval Process**  
  Enables financial institutions to approve loans more efficiently while minimizing default risks.
  
- **Improved Profitability**  
  Reducing defaults leads to a healthier loan portfolio, improving overall financial stability.
  
- **Enhanced Customer Relationships**  
  Allows banks to offer personalized interest rates and loan terms based on risk assessment.

## Dataset

### Dataset Information
The dataset used in this project comes from Kaggle [Loan Default Prediction](https://www.kaggle.com/competitions/credit-default-prediction-ai-big-data/overview) and consists of two files:
- **train.csv**: Includes customer features along with the target variable (Credit Default), which indicates whether a person defaulted on a loan.
- **test.csv**: Contains only customer features without the target variable, used for prediction.


### Data Considerations
- **Missing Values**: The dataset may contain missing values that require imputation.
- **Class Imbalance**: There may be class imbalance, with a significantly lower number of default cases (1) compared to non-default cases (0), necessitating resampling techniques.
- **Feature Engineering**: Some features might require transformation or engineering to enhance model performance.

## Workflow 

The Loan Default Prediction project follows a structured workflow to ensure comprehensive problem-solving. Key steps include:

1. **Business Understanding**  
   Defining the problem scope and understanding the financial impact of loan defaults, ensuring alignment with business objectives like minimizing risk and improving loan approval strategies.
   
2. **Data Understanding**  
   Analyzing the dataset to gain insights, including:
   - General data exploration
   - Identifying missing values and outliers
   - Using tools like Pandas Profiling for automated reports

3. **Data Preparation**  
   Preparing the dataset for modeling:
   - Handling missing values
   - Feature engineering (e.g., creating new features)
   - Encoding categorical variables and scaling numerical data

4. **Exploratory Data Analysis (EDA)**  
   Analyzing patterns and relationships between features:
   - Understanding variable correlations
   - Visualizing key trends and distributions
   - Extracting insights and key takeaways

5. **Modeling**  
   Developing machine learning models to predict loan defaults:
   - Training multiple models and selecting the best-performing one
   - The models used: Logistic Regression, LightGBM, and XGBoost
   - Evaluating models using metrics like accuracy, precision, recall, F1-score, and AUC-ROC
   - Optimizing hyperparameters for improved performance

**For a detailed explanation of the insights, processes, and reasoning behind each step, refer to the Notebook included in this repository.**

## Business Understanding

Loan default occurs when a borrower fails to meet scheduled repayments, leading to financial losses for lending institutions. Accurately predicting loan default risk is essential for banks and financial institutions to make informed lending decisions and minimize credit risk.

### Problem Statement
This project aims to develop a machine learning model to predict whether a loan applicant will default. By utilizing historical borrower data, the model will help financial institutions assess risk and make more effective lending decisions.

### Why Is This Important?
A reliable loan default prediction model can offer several benefits:
- **Risk Reduction**: Minimizes losses from non-performing loans (NPLs).
- **Improved Loan Approval Process**: Enables objective, data-driven decisions.
- **Optimized Credit Policies**: Adjusts interest rates and loan terms based on risk profiles.
- **Better Financial Stability**: Strengthens the financial health of lending institutions.

Understanding the factors behind loan defaults also provides insights for improving credit risk management and reducing bad debt.
