# DSA4263-Business-and-Commerce-Fraud-Detection
Welcome to the Bank Account Fraud Detection repository! We are a group of NUS students working on a Machine Learning project to detect fraudulent bank account applications using the NeurIPS 2022 Kaggle dataset.

## 🏦 Background
The Bank Account Fraud (BAF) suite of datasets was published at NeurIPS 2022 and consists of six synthetic tabular datasets designed to simulate fraud in bank account applications. BAF represents the first large-scale, realistic, and bias-aware testbed for evaluating both traditional and fairness-aware machine learning models in fraud detection.

The dataset we used is:

- Realistic, built on a present-day real-world dataset of fraudulent applications;
- Biased, with deliberately injected bias across features like age, employment status, and income percentile;
- Imbalanced, reflecting a very low prevalence of the positive (fraudulent) class, mimicking real-world fraud scenarios;
- Dynamic, containing temporal elements such as a month column to simulate distribution shifts over time;
- Privacy-preserving, employing differential privacy, feature obfuscation, and synthetic data generation via CTGAN to protect applicant identities.

This makes the BAF dataset highly suitable for developing, evaluating, and benchmarking fraud detection models in operational environments that demand robustness, fairness, and adaptability.

## 🔍 Approach
Due to limited documentation provided with the dataset, we began by conducting detailed exploratory data analysis (EDA) and applied domain knowledge to interpret and make assumptions about key features. Our pipeline involved several key steps: cleaning data by handling encoded missing values (such as -1) and imputing medians where necessary; engineering new features such as velocity ratios and binned income or credit score categories; encoding categorical variables using a mix of label and one-hot encoding; and applying SMOTE to address the severe class imbalance in fraud labels. We also implemented a temporal train-test split based on the month feature to mimic a realistic deployment scenario where models are trained on past data and tested on future behavior. Our model experimentation began with a baseline logistic regression, followed by challenger models including XGBoost and Random Forest. Although we initially tested GRU (Recurrent Neural Network) and Naive Bayes, they were eventually excluded due to their relatively poor performance. Our final model was an ensemble that blended predictions from XGBoost and Random Forest, with hyperparameters and blending weights tuned using Optuna to maximize AUC-PR performance on imbalanced validation data.

## Requirements
Do ensure your system or environment has the following dependencies installed as in requirements.txt

## Scripts
You may refer to the following notebooks in our Prod branch:
1. Exploratory Data Analysis and Cleaning (data_cleaning_and_eda.ipynb)
2. Logistic Regression (logisticregression.ipynb)
3. Random Forest (randomForestModel.ipynb)
4. Gradient Boosting (gradientBoosting.ipynb)
5. Model Ensemble (modelEnsemble.ipynb)

## Data dictionary
You may refer to data dictionary for descriptions of each variable of our chosen dataset. Raw data can be viewed from Kaggle: https://www.kaggle.com/datasets/sgpjesus/bank-account-fraud-dataset-neurips-2022/data 