Improving Bank Marketing Subscription Prediction with Revised Feature Engineering and Advanced Machine Learning Models

 Project Description
This project predicts whether a bank client will subscribe to a term deposit using the UCI Bank Marketing dataset. The business goal is to help marketing teams target customers more efficiently, reduce wasted outreach, and improve campaign effectiveness in an imbalanced classification setting.

Earlier modeling work used logistic regression, regularized logistic regression, and random forest as baseline approaches. In the final stage of this project, the modeling pipeline was improved by redesigning the feature engineering structure and comparing stronger models from later course topics. The revised feature engineering grouped predictors into contact history, campaign pressure, demographic/profile, financial, and time/macro blocks. Final model comparison focused on Lasso Logistic, Random Forest, tuned SVM, and tuned XGBoost.

The final results showed that the tuned SVM produced the strongest overall balanced performance after the revised feature engineering stage, while Random Forest remained useful as a higher-precision comparison model and Lasso Logistic remained a strong sparse baseline.

 Data Source
Dataset:
UCI Machine Learning Repository - Bank Marketing Dataset
https://archive.ics.uci.edu/dataset/222/bank+marketing

Main file used:
bank-additional.csv

Source description:
The dataset contains demographic, financial, campaign, and macroeconomic variables for direct telephone marketing campaigns by a Portuguese banking institution. The target variable is whether the client subscribed to a term deposit.

Important note:
The variable "duration" was excluded from the final prediction models because call duration is only known after the phone call ends and is therefore not suitable for a realistic pre-contact prediction setting.

 Folder Structure
After unzipping, the project folder should be arranged as follows:

XuWeiwei
├── data
│   ├── bank-additional.csv
│   └── readme_data.txt
├── ReadMe.txt
├── dsci_441_final_project.py
├── DSCI_441_Final_Project.ipynb
└── aux_1.py

 How to Prepare the Data
1. Use df = pd.read_csv('data/bank-additional.csv')
2. Make sure the file path used in the code matches the location of the dataset.

Expected path:
data/bank-additional.csv

 How to Run the Code
Directly use DSCI_441_Final_Project.ipynb.


 Model Pipeline Summary
The final modeling pipeline includes the following steps:

- Load and inspect the dataset
- Create binary target variable
- Exclude the leakage variable "duration"
- Apply revised feature engineering:
  - contact history features
  - campaign pressure features
  - demographic/profile features
  - financial features
  - time and macroeconomic features
- Split the data into training and testing sets
- Apply preprocessing with imputation, scaling, and one-hot encoding where appropriate
- Train and evaluate final models:
  - Lasso Logistic
  - Random Forest
  - Tuned SVM
  - Tuned XGBoost

 Final Model Results Summary
The final feature engineering produced the following main results:

- Tuned SVM achieved the highest balanced accuracy and the strongest overall balanced performance.
- Lasso Logistic remained a strong baseline for recall-oriented classification.
- Random Forest achieved the highest precision among the final models.
- Tuned XGBoost improved after revised feature engineering, but it did not surpass the tuned SVM.

These results suggest that revised feature engineering combined with tuned SVM provided the best tradeoff for this project.

 How to Run the Streamlit App
The interactive web app allows users to:
- review the project overview
- compare final model performance
- explore customer-level prediction behavior
- support campaign targeting decisions

To run the app:

streamlit run aux_1.py

Then open the local Streamlit link shown in the terminal.