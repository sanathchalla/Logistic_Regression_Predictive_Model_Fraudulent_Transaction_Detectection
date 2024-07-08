# Credit Card Fraud Detection using Logistic Regression

## Project Summary

This project focuses on building a predictive model using Logistic Regression to detect fraudulent credit card transactions. The dataset used for this project was sourced from Kaggle (https://www.kaggle.com/ealaxi/paysim1) and involves several steps including data preprocessing, feature engineering, model training, and evaluation.

Dataset Description

The dataset comprises simulated mobile money transactions, with 6,362,620 total transactions, out of which 8,213 are labeled as fraudulent. The dataset includes the following columns:

step: Time step (hour)

type: Type of transaction (CASH-IN, CASH-OUT, DEBIT, PAYMENT, TRANSFER)

amount: Amount of the transaction

nameOrig: Customer initiating the transaction

oldbalanceOrg: Initial balance before the transaction

newbalanceOrig: New balance after the transaction

nameDest: Recipient of the transaction

oldbalanceDest: Initial balance of the recipient before the transaction

newbalanceDest: New balance of the recipient after the transaction

isFraud: Indicator if the transaction is fraudulent (1) or not (0)

## Methodology

1. Data Preprocessing
   
Loading Data: Imported the dataset into a pandas DataFrame.
Initial Inspection: Displayed the first 10 rows and basic information about the dataset to understand its structure and check for missing values.

2. Feature Engineering
   
Transaction Types: Identified unique transaction types and created two new features:
isPayment: Indicates if the transaction type is PAYMENT or TRANSFER.
isMovement: Indicates if the transaction type is DEBIT or CASH-OUT.
Account Balance Difference: Created a new feature accountDiff to represent the absolute difference between the origin and destination balances, which helps in identifying potential fraudulent activities.

3. Splitting the Dataset
   
Features and Labels: Defined features (amount, isPayment, isMovement, accountDiff) and label (isFraud).
Train-Test Split: Split the dataset into training and testing sets using a 70-30 split.

4. Normalization
   
Standardization: Applied StandardScaler to standardize the features, ensuring the logistic regression model performs well.

5. Model Training and Evaluation
   
Logistic Regression: Trained a logistic regression model on the training data.
Model Performance: Evaluated the model using the training and test data, achieving a high accuracy of 99%.
Model Coefficients: Analyzed the coefficients of the trained model.

6. Prediction
 
New Transactions: Created sample transactions and normalized them using the previously fitted scaler.
Fraud Detection: Used the trained model to predict whether these new transactions are fraudulent or not.

## Results

The logistic regression model demonstrated high accuracy in detecting fraudulent transactions. It was able to correctly classify both the training and testing data with an accuracy of 99%. When tested on new sample transactions, the model did not classify any of them as fraudulent, indicating its reliability in predicting fraud.

## Conclusion

This project successfully built a predictive model using logistic regression to detect fraudulent transactions with high accuracy. The key steps involved data preprocessing, feature engineering, model training, and evaluation. The results show that logistic regression is a suitable method for this classification task, providing a robust solution for fraud detection in credit card transactions.
