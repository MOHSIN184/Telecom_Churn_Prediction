# Telecom Customer Churn Project

This repository contains a structured Jupyter notebook workflow for analyzing telecom customer churn, from project definition through dataset understanding, preprocessing, modeling, and business insights.

## Project Flow

1. `1_Project_Overview.ipynb`
   - Defines the business problem: predicting telecom customer churn.
   - Describes objectives, success metrics, assumptions, and project impact.
   - Presents the end-to-end workflow from data understanding to deployment.
   - Serves as the project roadmap for the remaining notebooks.

2. `2. About_Dataset.ipynb`
   - Introduces the dataset source and key attributes.
   - Loads the raw dataset from `Telco_customer_churn.xlsx`.
   - Displays the first, last, and sample rows to verify the dataset contents.
   - Documents critical columns such as customer demographics, contract details, billing information, churn label, and churn reason.

3. `3. EDA.ipynb`
   - Performs exploratory data analysis to understand data structure, distributions, and relationships.
   - Checks data types, summary statistics, missing values, and outliers.
   - Visualizes feature distributions for numerical fields like `Monthly Charges` and `Total Charges`.
   - Analyzes categorical variables such as `Contract`, `Payment Method`, and `Churn Label`.
   - Examines churn segmentation by contract type, payment method, and gender.
   - Computes a correlation matrix to highlight strong feature relationships.

4. `4. Data_Processing.ipynb`
   - Prepares the dataset for modeling.
   - Replaces empty strings with missing values and handles missing data appropriately.
   - Imputes missing `Total Charges` values using `Monthly Charges * Tenure Months`.
   - Fills missing churn reasons with `no_reason_given` for non-churned customers.
   - Drops irrelevant columns such as geographic identifiers and redundant churn-related fields.
   - Converts data types and encodes categorical variables using `LabelEncoder`.
   - Applies scaling to numerical features and saves the processed dataset to `Telco_customer_churn_processed.xlsx`.

5. `5. Model_Implementation.ipynb`
   - Loads the processed dataset from `Telco_customer_churn_processed.xlsx`.
   - Splits data into training, validation, and test sets (70/15/15 split).
   - Applies `StandardScaler` to numeric features.
   - Trains an `XGBoost` classification model on the training set.
   - Evaluates the model using accuracy, classification report, confusion matrix, and ROC AUC.
   - Builds a model dashboard summarizing dataset composition, performance metrics, top features, and business interpretation.

6. `6. Business_Insights.ipynb`
   - Focuses on business insights and actionable recommendations.
   - Uses a cleaned BI dataset file `Telco_customer_churn_cleaned(For BI).xlsx`.
   - Ranks churn reasons and identifies the most common drivers.
   - Highlights tenure-based risk segments and churn patterns by contract and internet service.
   - Produces charts and narrative recommendations for customer support, retention, and competitive offer strategy.

## Recommended Notebook Order

Use the notebooks sequentially to follow the full pipeline:

1. `1_Project_Overview.ipynb`
2. `2. About_Dataset.ipynb`
3. `3. EDA.ipynb`
4. `4. Data_Processing.ipynb`
5. `5. Model_Implementation.ipynb`
6. `6. Business_Insights.ipynb`

## Key Files

- `Telco_customer_churn.xlsx` — raw dataset loaded in `2. About_Dataset.ipynb` and `3. EDA.ipynb`.
- `Telco_customer_churn_processed.xlsx` — cleaned and encoded dataset produced by `4. Data_Processing.ipynb` and `5. Model_Implementation.ipynb`.
- `Telco_customer_churn_cleaned(For BI).xlsx` — BI-focused cleaned dataset used in `6. Business_Insights.ipynb`.

## Purpose of Each Notebook

- `1_Project_Overview.ipynb`: Project definition and planning.
- `2. About_Dataset.ipynb`: Dataset introduction and initial loading.
- `3. EDA.ipynb`: Exploratory Data Analysis and feature understanding.
- `4. Data_Processing.ipynb`: Data cleaning, imputation, encoding, and scaling.
- `5. Model_Implementation.ipynb`: Model training, evaluation, and performance reporting.
- `6. Business_Insights.ipynb`: Business-focused insights and retention recommendations.

## Tools and Libraries Used

- Python
- pandas
- NumPy
- Matplotlib
- Seaborn
- scikit-learn
- XGBoost

## Notes

- `6. Business_Insights.ipynb` is designed for stakeholders and focuses on interpretability rather than model training.
- The workflow is built to move from raw data exploration to a trained model and then to business action.
- If you want to re-run the full analysis, start with `2. About_Dataset.ipynb` to load the raw data and follow the notebook order listed above.
