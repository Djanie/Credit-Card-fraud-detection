# Credit-Card-fraud-detection
A credit card fraud detection project to differentiate between fraudulent and legitimate transactions

This project focuses on building a machine learning model to detect fraudulent credit card transactions. With the rise of digital transactions, detecting fraud in real time has become a critical challenge for financial institutions. This project tackles the problem of credit card fraud detection using several machine learning algorithms, with a particular focus on handling the imbalanced nature of the dataset, where fraudulent transactions represent a tiny fraction of the total transactions.

The project covers data preprocessing, model building, and performance evaluation using metrics like the Area Under the ROC Curve (AUC-ROC), Precision-Recall, and F1-Score. The final goal is to create a model that can efficiently distinguish between fraudulent and legitimate transactions.

Problem Statement
Credit card fraud causes financial institutions to lose billions of dollars annually. Fraudulent transactions are highly infrequent, making it a classic example of an imbalanced classification problem. Our objective is to build a machine learning model that:

Maximizes the detection of fraudulent transactions (high recall).
Minimizes false positives to avoid inconveniencing legitimate customers (precision).
Handles the imbalanced dataset efficiently.

Dataset
The dataset used for this project contains credit card transactions made in September 2013 by European cardholders. It includes 31 features: 28 anonymized numerical features obtained via a PCA transformation, along with Time, Amount, and a Class label, where:

0 = Legitimate transactions
1 = Fraudulent transactions

Dataset Challenges:
Imbalanced Classes: Only about 0.17% of the transactions are fraudulent.
High Dimensionality: The dataset contains 31 features, making feature selection important.
Feature Scaling: The Amount and Time columns require scaling since they are not part of the PCA-transformed features.

Project Pipeline
1. Data Preprocessing
Data Cleaning: No missing values were detected in the dataset, so no imputation was necessary.
Feature Scaling: We applied StandardScaler to the Amount and Time columns to normalize them for model training.
Splitting the Data: The dataset was split into training and testing sets using a stratified split to preserve the ratio of fraud-to-non-fraud transactions in both sets.
2. Handling Imbalanced Data
To overcome the extreme class imbalance, we applied the Synthetic Minority Over-sampling Technique (SMOTE). SMOTE synthetically generates new samples for the minority class (fraudulent transactions) to balance the dataset and help the model better identify fraud.
3. Performance Metrics
AUC-ROC Curve: Used to measure the model's ability to distinguish between fraud and legitimate transactions.
Precision-Recall Curve: Since we are more interested in detecting fraud (recall) while also minimizing false positives (precision), this curve provides critical insights.
Confusion Matrix: To visualize true positives, false positives, true negatives, and false negatives.
Classification Report: Showed precision, recall, and F1-score for both classes.

Key Findings
Imbalanced Data Handling: Using SMOTE helped significantly improve the model's ability to detect fraud by oversampling the minority class. Without it, models struggled to identify fraudulent transactions.
Random Forest Performance: The Random Forest classifier demonstrated excellent results with an AUC score of 0.95, meaning it was able to effectively differentiate between fraud and non-fraud transactions.
Model Limitations: While the recall for fraud detection was high, precision suffered slightly, meaning the model occasionally flagged legitimate transactions as fraudulent.

Visualizations
AUC-ROC Curve: Demonstrates the model's performance across different classification thresholds.
Precision-Recall Curve: Shows the balance between precision and recall for the models, helping to tune for better fraud detection.
Confusion Matrix: Visualizes the true and false positives/negatives, giving a snapshot of model accuracy.
Conclusion
This project demonstrates that machine learning can be a powerful tool in detecting credit card fraud, especially when combined with techniques like SMOTE to handle imbalanced data. The use of Random Forest and Logistic Regression proved effective, with Random Forest outperforming in terms of AUC-ROC.
