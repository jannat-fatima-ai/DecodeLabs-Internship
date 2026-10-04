# Project 2: Supervised Learning — Fraud Detection Pipeline

## Project Objective

The objective of this project is to build a supervised machine learning pipeline for detecting fraudulent credit card transactions.

Because fraudulent transactions are highly imbalanced compared with genuine transactions, SMOTE (Synthetic Minority Over-sampling Technique) is used to handle class imbalance.

Two classification algorithms were implemented:

- Logistic Regression
- Random Forest

The models were evaluated using Precision, Recall, and ROC-AUC rather than relying on Accuracy.

## Dataset

The project uses the Credit Card Fraud Detection dataset from the Machine Learning Group - ULB.

Dataset source:

https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

The original dataset contains 284,807 transactions and 30 input features.

After removing duplicate records, 283,726 transactions remained.

The target variable is `Class`:

- `0` = Genuine transaction
- `1` = Fraudulent transaction

The dataset is highly imbalanced, with fraudulent transactions representing a very small portion of all transactions.

## Data Preprocessing

The following preprocessing steps were performed:

1. Loaded the credit card transaction dataset.
2. Checked for missing values.
3. Identified and removed duplicate records.
4. Separated the target variable `Class` from the input features.
5. Split the data into training and testing sets using an 80/20 stratified split.

The test set was kept separate and untouched during model training and hyperparameter tuning.

## Handling Class Imbalance

SMOTE was used to address the severe class imbalance.

SMOTE was placed inside the machine learning pipelines so that oversampling was performed only on the training folds during cross-validation.

This approach helps prevent data leakage from the training data into the validation or test data.

## Machine Learning Models

### Logistic Regression

The Logistic Regression pipeline contains:

- StandardScaler
- SMOTE
- Logistic Regression

GridSearchCV with 5-fold Stratified Cross-Validation was used for hyperparameter tuning.

Best parameters:

- C = 0.1
- Solver = lbfgs
- SMOTE k_neighbors = 3

Best cross-validation ROC-AUC: approximately 0.9815

### Random Forest

The Random Forest pipeline contains:

- SMOTE
- Random Forest Classifier

GridSearchCV with 5-fold Stratified Cross-Validation was used for hyperparameter tuning.

Best parameters:

- n_estimators = 100
- max_depth = 10
- SMOTE k_neighbors = 5

Best cross-validation ROC-AUC: approximately 0.9812

## Test Set Results

| Model | Precision | Recall | ROC-AUC |
|---|---:|---:|---:|
| Logistic Regression | 0.0528 | 0.8737 | 0.9637 |
| Random Forest | 0.6016 | 0.8105 | 0.9733 |

### Results Interpretation

Logistic Regression achieved higher recall, detecting a larger proportion of fraudulent transactions.

Random Forest achieved higher precision and ROC-AUC, providing fewer false fraud alerts and stronger overall ranking performance on the test set.

The preferred model therefore depends on the specific fraud detection objective.

## Visualizations

The project includes the following visualizations:

- Fraud vs Genuine Transaction Distribution
- Confusion Matrix — Logistic Regression
- Confusion Matrix — Random Forest
- ROC Curve
- Model Performance Comparison
- Top 10 Random Forest Feature Importances
- Class Distribution Before and After SMOTE

## Feature Importance

The top Random Forest features were:

1. V14
2. V10
3. V12
4. V17
5. V4
6. V3
7. V11
8. V16
9. V2
10. V9

V14 was the most important feature according to the trained Random Forest model.

## Project Outputs

The `output` folder contains:

- `model_results.csv`
- `model_predictions.csv`
- `feature_importance.csv`
- `logistic_regression_gridsearch_results.csv`
- `random_forest_gridsearch_results.csv`

The `visualizations` folder contains the generated charts and evaluation plots.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-Learn
- Imbalanced-Learn
- Jupyter Notebook

## Project Notebook

Main notebook:

`Project_2_Fraud_Detection.ipynb`

## How to Run

1. Download the dataset from the Kaggle source mentioned above.
2. Extract `creditcard.csv`.
3. Place it inside:

`data/raw/creditcard.csv`

4. Open `Project_2_Fraud_Detection.ipynb`.
5. Install the required Python packages.
6. Run all notebook cells from top to bottom.

## Conclusion

This project demonstrates a complete supervised machine learning pipeline for credit card fraud detection, including data preprocessing, class imbalance handling with SMOTE, model training, hyperparameter tuning, 5-fold cross-validation, and evaluation using Precision, Recall, ROC-AUC, and confusion matrices.