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

## Notable Insight from EDA

From Exploratory Data Analysis (EDA), there are several interesting findings as follows:

### Low Credit Score, High Risk
![Credit Score vs Credit Default](https://github.com/RaihanWinurputra/LoanDefaultPrediction/blob/main/Image/Credit%20Score%20vs%20Credit%20Default.png)  
A borrower's credit score exhibits a strong inverse correlation with their likelihood of default, with lower credit scores corresponding to a substantially increased risk of default. The marked peak around a credit score of 720 suggests that this score may represent a critical threshold in lending decisions, guiding risk assessments and credit approval processes. Borrowers with scores below 700 face a significantly elevated risk of default, highlighting the need for lenders to exercise heightened scrutiny when evaluating such applications. By adopting tailored strategies for this risk segment, lenders can better manage potential losses while ensuring prudent lending practices.

### Stable Employment, Lower Risk
![Years in Current Job vs Credit Default](https://github.com/RaihanWinurputra/LoanDefaultPrediction/blob/main/Image/Years%20in%20Current%20Job%20vs%20Credit%20Default.png)  
Job stability, as reflected in longer employment tenure—especially around the 10-year mark—plays a pivotal role in reducing default risk. Borrowers with extended job histories often demonstrate a reliable and steady source of income, which enhances their financial resilience and ability to meet repayment obligations. Stable employment not only signals consistent earnings but also suggests a level of responsibility and commitment, traits that are highly valued by lenders. Consequently, individuals with lengthy employment records are typically regarded as more dependable and lower-risk borrowers.

### Financial Vulnerability and Credit Default
![Income vs Credit Default](https://github.com/RaihanWinurputra/LoanDefaultPrediction/blob/main/Image/Annual%20Income%20vs%20Credit%20Default.png)  
Income level is a critical factor in assessing the likelihood of loan default. Borrowers with lower annual incomes often face greater financial constraints, which can hinder their ability to meet repayment obligations consistently. Limited income may reduce their capacity to absorb unexpected expenses or economic shocks, increasing the risk of missed payments or default. Consequently, lenders often consider income stability and sufficiency when evaluating a borrower's creditworthiness.

### Debt to Income Ratio
![Debt to Income Ratio vs Credit Default](https://github.com/RaihanWinurputra/LoanDefaultPrediction/blob/main/Image/Debt%20to%20Income%20Ratio.png)  
A higher debt-to-income (DTI) ratio is closely linked to an increased risk of loan default, with borrowers exceeding the 0.15–0.20 range warranting closer monitoring. The majority of defaults are observed within the DTI range of 0.10–0.30, indicating that this span may serve as a critical zone for assessing financial vulnerability. This pattern highlights the importance of DTI as a key metric for lenders when refining risk assessment models. By identifying and addressing borrowers with elevated DTI ratios, lenders can proactively mitigate potential defaults and enhance the overall robustness of their credit evaluation processes.


## Modeling

### Models Used
The following models were implemented to evaluate their performance and robustness:
- **Logistic Regression**: A statistical model often used for binary classification problems, serving as a baseline in this project.
- **LightGBM**: A gradient-boosting framework that excels in handling large datasets and producing high-performance results.
- **XGBoost**: Another powerful gradient-boosting algorithm known for its speed and performance in machine learning competitions.

### Modeling Conditions
To address the imbalance in the target variable, modeling was performed under three distinct conditions:
1. **Without Handling Imbalance**: The models were trained on the original, imbalanced dataset, serving as a benchmark.
2. **Cost-Sensitive Learning**: Model training incorporated cost-sensitive adjustments to penalize misclassification of minority class instances.
3. **Synthetic Minority Oversampling Technique (SMOTE)**: Synthetic data generation was used to balance the dataset by oversampling the minority class.

### Model Summary
![Model Evaluation Scores](https://github.com/RaihanWinurputra/LoanDefaultPrediction/blob/main/Image/Model%20Evaluation%20Scores.png)  

For predicting loan defaults, **LightGBM with Cost-Sensitive Learning** stands out as the best model. It strikes a great balance by:

- Catching the most defaulters (highest recall: **0.64**).
- Balancing precision and recall effectively (highest **F1 score**: **0.5773**).
- Delivering the strongest overall performance (highest **ROC-AUC**: **0.8098**).

This model reduces missed defaulters, lowers financial risks, and ensures reliable predictions, making it the top choice for loan default prediction.

