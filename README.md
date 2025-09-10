# Loan Prediction Project
This project focuses on predicting loan status based on a dataset of loan applicants. The primary goal is to build a reliable machine learning model that can determine whether a loan will be approved or denied. This README provides a comprehensive overview of the project, including data analysis, feature engineering, and model development.

## Table of Contents
1. Project Overview
2. Exploratory Data Analysis (EDA)
3. Feature Engineering
4. Model Development and Training
5. Evaluation

## Project Overview
The main objective of this project is to create a model that accurately predicts loan outcomes. By analyzing various applicant attributes, we can identify key factors that influence loan approval and build a predictive model to assist in the decision-making process. The dataset used in this project is loan_data.csv.

Dataset Link: [Download](https://github.com/arunava6/loan_prediction_project/raw/refs/heads/main/loan_data.csv)

## Exploratory Data Analysis (EDA)
The first step in our analysis was to explore the dataset to gain a deeper understanding of its structure and uncover any underlying patterns.

### Data Loading and Initial Assessment:

a. The dataset was loaded using pandas, and an initial assessment was conducted to check for any missing values. No missing data was found, ensuring a clean dataset for our analysis.

b. The columns were renamed for better readability (e.g., person_age to age).

### Visualizing Key Relationships:

a. A histogram of the loan_amnt showed that most loan amounts are concentrated in the lower range, with a few larger loans.
<img width="600" height="400" alt="Screenshot 2025-09-09 225911" src="https://github.com/user-attachments/assets/f5233c9c-644b-4fe4-9e1d-3fd094d1d043" />

b. A boxplot comparing loan_int_rate and loan_status revealed that loans with higher interest rates are more likely to be denied.
<img width="600" height="400" alt="Screenshot 2025-09-09 230003" src="https://github.com/user-attachments/assets/53c5be1f-0e80-4f8a-8243-84eab876042e" />

c. A countplot was used to examine the relationship between loan_status and loan_default. This showed a clear correlation between defaulting on a previous loan and the outcome of the current loan application.
<img width="600" height="400" alt="Screenshot 2025-09-09 230026" src="https://github.com/user-attachments/assets/1afa3820-57e1-4a82-9387-2c78f3c89356" />

d. Another countplot illustrated how home_ownership relates to loan_status, providing insights into how different housing situations affect loan approvals.
<img width="600" height="400" alt="Screenshot 2025-09-09 230051" src="https://github.com/user-attachments/assets/cf39adf2-10b2-4b3c-ac36-1f4b1ebdb35d" />

## Feature Engineering
To prepare the data for our machine learning model, several feature engineering techniques were applied:

### One-Hot Encoding:

Categorical features with multiple distinct values, such as education, home_ownership, and loan_intent, were converted into a numerical format using one-hot encoding. This creates new binary columns for each category, allowing the model to interpret them effectively.

### Label Encoding:

For binary categorical features like gender and loan_default, label encoding was used. This technique converts categories into numerical values (e.g., 0 and 1), making them suitable for the model.

### Z-Score Standardization:

Numerical columns, including age, income, emp_exp, and loan_amnt, were standardized using the StandardScaler. This scales the data to have a mean of 0 and a standard deviation of 1, which helps the model perform better by preventing features with larger scales from dominating the learning process.

## Model Development and Training
With the data prepared, we moved on to building and training our predictive model.

### Data Splitting:

The dataset was divided into training and testing sets, with 80% of the data used for training the model and the remaining 20% reserved for testing its performance. The loan_status and credit_score columns were designated as the target variables.

### Model Selection:

A Random Forest Classifier was chosen for this task. This model is well-suited for classification problems and is known for its high accuracy and ability to handle complex datasets.

## Evaluation
After training the model, its performance was evaluated using several key metrics:

Accuracy: The model achieved an accuracy of approximately 92.88% on the test set, indicating a high level of correctness in its predictions.

F1 Score: The F1 score, which balances precision and recall, was about 81.87%. This shows that the model is effective at identifying both positive and negative cases.

Cross-Validation: To ensure the model's stability, 8-fold cross-validation was performed. The results were consistent, with an average accuracy of 92.61% and an F1 score of 81.97%.

The confusion matrix also confirmed the model's strong performance, showing a high number of correct predictions for both loan approvals and denials.
