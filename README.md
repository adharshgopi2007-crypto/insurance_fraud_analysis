# Insurance Claims Fraud Analysis

## Overview

This project analyzes insurance claims data to identify patterns associated with reported fraud and explores whether machine learning can be used to predict fraudulent claims.

The analysis uses Python to clean the data, perform exploratory data analysis, create visualizations, and build classification models.

## Dataset

The dataset contains 1,000 insurance claim records with information about policyholders, policies, incidents, claim amounts, vehicles, and reported fraud.

The target variable is `fraud_reported`, which indicates whether a claim was reported as fraudulent.

## Tools and Technologies

- Python
- Pandas
- Matplotlib
- Scikit-learn
- Jupyter Notebook
- VS Code

## Data Cleaning

The dataset was checked for missing values and unnecessary columns.

- Removed a fully null column
- Replaced missing values in `authorities_contacted` with `Unknown`
- Verified that no missing values remained before analysis

## Exploratory Data Analysis

Several claim characteristics were analyzed to identify differences in reported fraud rates.

### Key Findings

- Major damage claims had a reported fraud rate of approximately 60%, substantially higher than the other incident severity categories.
- Single-vehicle collisions had a reported fraud rate of approximately 29%.
- Multi-vehicle collisions had a reported fraud rate of approximately 27%.
- Parked car and vehicle theft claims had substantially lower reported fraud rates, at approximately 9.5% and 8.5%.
- Fraudulent claims had a somewhat higher median total claim amount, although there was substantial overlap between fraudulent and non-fraudulent claims.

These findings represent associations within the dataset and do not establish that any individual characteristic causes fraud.

## Machine Learning

Two classification approaches were explored:

- Logistic Regression
- Random Forest

The data was divided into training and testing sets. Categorical variables were one-hot encoded before being provided to the models.

The Random Forest model achieved approximately:

- **82.5% accuracy**
- **73% fraud recall**
- **62% fraud precision**
- **67% fraud F1-score**

These metrics show how the model performed on the held-out test set and should be interpreted together rather than relying on accuracy alone.

## Feature Importance

Random Forest feature importance was used to examine which features contributed most to the model's predictions.

Incident severity was particularly important, with the `Major Damage` category being the highest individual encoded feature. This was consistent with the exploratory analysis, where major damage claims had a substantially higher reported fraud rate.

Feature importance measures predictive usefulness within the model and does not imply causation.

## Project Structure

```text
insurance-fraud-analysis/
│
├── insurance_analysis.ipynb
├── README.md
├── .gitignore