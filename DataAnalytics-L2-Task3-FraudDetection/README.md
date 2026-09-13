# Fraud Detection Using Machine Learning

## Project Overview

This project focuses on developing a Machine Learning solution for detecting fraudulent credit card transactions in a highly imbalanced financial dataset.

The project addresses the challenges of fraud detection by applying SMOTE (Synthetic Minority Oversampling Technique) to the training data and comparing the performance of Logistic Regression and Random Forest models.

Model performance is evaluated using Precision, Recall, F1-Score, and AUC-ROC, with particular emphasis on the trade-off between detecting fraudulent transactions and minimizing false alerts.

## Dataset

The dataset contains 284,807 credit card transactions with 30 input features and one target variable.

| Dataset Information | Value |
|---|---:|
| Total Transactions | 284,807 |
| Input Features | 30 |
| Fraudulent Transactions | 492 |
| Non-Fraudulent Transactions | 284,315 |
| Fraudulent Transactions | 0.173% |
| Non-Fraudulent Transactions | 99.827% |

The dataset consists of anonymized PCA-transformed features (V1–V28), along with Time and Amount.

The target variable is:

- 0 → Non-Fraudulent Transaction
- 1 → Fraudulent Transaction

## Objectives

- Analyze the distribution of fraudulent and non-fraudulent transactions.
- Identify the impact of severe class imbalance.
- Analyze transaction amount and time-of-day patterns.
- Apply SMOTE to address class imbalance.
- Perform a stratified train-test split.
- Train Logistic Regression and Random Forest models.
- Evaluate models using Precision, Recall, F1-Score, and AUC-ROC.
- Analyze the most influential features.
- Understand the Precision-Recall trade-off in fraud detection.
- Discuss scalability for large-scale transaction processing.

## Technologies Used

Python | Pandas | NumPy | Scikit-learn | Imbalanced-learn | Matplotlib | Seaborn | Jupyter Notebook

## Methodology

The project follows the following Machine Learning workflow:

Data Loading → Exploratory Data Analysis → Class Imbalance Analysis → Transaction Amount Analysis → Time-of-Day Analysis → Stratified Train-Test Split → SMOTE → Model Training → Model Evaluation → ROC-AUC Analysis → Feature Importance → Fraud Detection Insights

## Class Imbalance Handling

The dataset contains a very small proportion of fraudulent transactions. Therefore, SMOTE was applied only to the training data to prevent data leakage and maintain a realistic test set.

| Stage | Non-Fraud | Fraud |
|---|---:|---:|
| Before SMOTE | 227,451 | 394 |
| After SMOTE | 227,451 | 227,451 |

The original test dataset was kept unchanged for reliable evaluation.

## Models Used

### 1. Logistic Regression

Logistic Regression was used as a baseline classification model. Feature scaling was applied using StandardScaler.

### 2. Random Forest

Random Forest was used as the second classification model with:

- n_estimators = 100
- random_state = 42

Random Forest was selected to provide a stronger non-linear classification approach and enable feature importance analysis.

## Model Performance

| Model | Precision | Recall | F1-Score | AUC-ROC |
|---|---:|---:|---:|---:|
| Logistic Regression | 0.1341 | 0.8980 | 0.2334 | 0.9765 |
| Random Forest | 0.8351 | 0.8265 | 0.8308 | 0.9644 |

## Model Comparison

Random Forest achieved a significantly better balance between Precision and Recall.

Random Forest Performance:

- Precision: 83.51%
- Recall: 82.65%
- F1-Score: 83.08%
- AUC-ROC: 96.44%

Logistic Regression achieved a higher Recall of 89.80% and AUC-ROC of 97.65%, but its Precision was only 13.41%, resulting in a much higher number of false fraud alerts.

Therefore, Random Forest was selected as the preferred model for this project based on its stronger overall Precision-Recall balance and F1-Score.

## Precision-Recall Trade-off

In fraud detection, Recall is particularly important because failing to identify an actual fraudulent transaction can result in financial loss.
However, maximizing Recall alone can generate a large number of false positives. Precision is therefore also important because it helps reduce unnecessary fraud alerts and manual investigations.

The preferred operating point depends on the business cost of:

- Missing a fraudulent transaction.
- Investigating a legitimate transaction incorrectly flagged as fraud.

## Feature Importance

Random Forest feature importance analysis identified the following features as the most influential:

| Rank | Feature | Importance |
|---:|---|---:|
| 1 | V14 | 0.217013 |
| 2 | V10 | 0.119797 |
| 3 | V4 | 0.116789 |
| 4 | V12 | 0.107501 |
| 5 | V17 | 0.086248 |

V14 was identified as the most influential feature in the Random Forest model.

## Key Insights

- The dataset is highly imbalanced, with fraudulent transactions representing only 0.173% of all transactions.
- Accuracy alone is not an appropriate evaluation metric for this type of problem.
- SMOTE effectively balanced the training dataset while keeping the test dataset unchanged.
- Logistic Regression achieved higher Recall but generated substantially more false positives.
- Random Forest provided a stronger overall balance between Precision, Recall, and F1-Score.
- Random Forest achieved an F1-Score of 83.08%.
- V14 was the most influential feature according to Random Forest feature importance.
- Fraud detection systems should consider both model performance and the business cost of false positives and false negatives.

## Scalability

For processing approximately 1 million transactions per hour, the fraud detection system could be deployed using a scalable architecture involving:

Incoming Transactions → Data Processing → Fraud Detection Model → Fraud Probability → Decision → Alert / Approval

A production system could use:

- Real-time API-based model deployment.
- Batch or streaming transaction processing.
- Parallel processing for high transaction volumes.
- Cloud-based scalable infrastructure.
- Automated fraud alerts for suspicious transactions.
- Periodic model retraining using newly verified transactions.

## Conclusion

This project demonstrates how Machine Learning can be applied to fraud detection in a highly imbalanced financial dataset.

The use of SMOTE, combined with Logistic Regression and Random Forest, provided an effective framework for identifying fraudulent transactions. While Logistic Regression achieved higher Recall and AUC-ROC, Random Forest provided a substantially stronger balance between Precision, Recall, and F1-Score.

Based on the overall evaluation, Random Forest was selected as the preferred model for this project.

