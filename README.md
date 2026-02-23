# Creditcard_fraud_detection
Credit Card Fraud Detection – Research Replication : This project replicates a research paper proposing a DBSCAN-augmented disjunctive ensemble for fraud detection.


Here is a clean, professional, and human-toned README file without emojis:

---

# Credit Card Fraud Detection using DBSCAN-Augmented Ensemble

Research Paper Replication

## Overview

This project is a replication of a research paper that proposes improving credit card fraud detection using a DBSCAN-augmented disjunctive ensemble model. The objective is to reproduce the methodology described in the paper and evaluate whether combining clustering-based feature augmentation with ensemble voting improves fraud detection performance under imbalanced conditions.

## Dataset

The experiments use the Kaggle 2023 Credit Card Fraud dataset (`creditcard_2023.csv`).
The target variable is defined as:

* 0 – Legitimate transaction
* 1 – Fraudulent transaction

To simulate realistic fraud scenarios, controlled 1% fraud subsets were created with different dataset sizes:

* 40,400 records
* 80,800 records
* 121,200 records

Each subset maintains the same fraud ratio to evaluate model behavior across different scales.

## Methodology

1. **Preprocessing**
   Missing values are removed, and features are standardized using StandardScaler to ensure fair contribution across all variables.

2. **DBSCAN Feature Augmentation**
   Iterative DBSCAN clustering is applied, and the resulting cluster labels are appended as additional features. This step enriches the feature space by incorporating density-based structural information.

3. **Model Training**
   Three classifiers are trained:

   * Random Forest
   * K-Nearest Neighbors (KNN)
   * Support Vector Machine (RBF kernel)

4. **Disjunctive Voting**
   A transaction is classified as fraud if any of the classifiers predicts fraud. This approach prioritizes maximizing fraud recall.

## Evaluation

Model performance is evaluated using:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix

Special emphasis is placed on recall for the fraud class to reduce missed fraudulent transactions.

## Objective

The primary goal of this project is to replicate the proposed research methodology, validate its effectiveness, and analyze the impact of DBSCAN-based feature augmentation combined with ensemble learning for fraud detection.

---

If you would like, I can also add sections for installation, usage instructions, or citation of the original research paper.
