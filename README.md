# DSA4263-Business-and-Commerce-Fraud-Detection

Welcome to the Bank Account Fraud Detection repository! We are a group of NUS students working on a Machine Learning project to detect fraudulent bank account applications using the NeurIPS 2022 Kaggle dataset.

🏦 Background
The Bank Account Fraud (BAF) suite of datasets was published at NeurIPS 2022 and consists of six synthetic tabular datasets designed to simulate fraud in bank account applications. BAF represents the first large-scale, realistic, and bias-aware testbed for evaluating both traditional and fairness-aware machine learning models in fraud detection.

The dataset we used is:

- Realistic, built on a present-day real-world dataset of fraudulent applications;

- Biased, with deliberately injected bias across features like age, employment status, and income percentile;

- Imbalanced, reflecting a very low prevalence of the positive (fraudulent) class, mimicking real-world fraud scenarios;

- Dynamic, containing temporal elements such as a month column to simulate distribution shifts over time;

- Privacy-preserving, employing differential privacy, feature obfuscation, and synthetic data generation via CTGAN to protect applicant identities.

This makes the BAF dataset highly suitable for developing, evaluating, and benchmarking fraud detection models in operational environments that demand robustness, fairness, and adaptability.

🔍 Approach
Due to limited documentation, we conducted thorough exploratory data analysis (EDA) and used domain knowledge to interpret features. Our pipeline included:

- Data cleaning (handling encoded missing values like -1, imputing medians)

- Feature engineering (ratios, binning income/credit scores)

- Encoding (label + one-hot encoding)

- Resampling using SMOTE to address class imbalance

- Temporal train-test split using the month feature to simulate real-world deployment

We trained and evaluated multiple models:

- Baseline: Logistic Regression

- Challengers: XGBoost and Random Forest (GRU - Recurrent Neural Network and Naive Bayes removed due to poor performance)

- Final Ensemble: Blended model combining XGBoost and Random Forest using Optuna for hyperparameter and weight tuning