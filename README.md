# Credit Card Fraud Detection Using Ensemble and Hybrid Models

This repository contains my implementation and evaluation of **machine learning models for credit card fraud detection**.
The work is based on an ensemble and hybrid approach proposed in a recent research paper, and I test the same idea on the **Kaggle Credit Card Fraud dataset** to see how well it performs on a real, highly imbalanced dataset.

The main goal of this project is to compare **individual classifiers** with **ensemble methods**, and to study the effect of combining supervised learning with **DBSCAN-based clustering**.

---

## Objectives

* Train and evaluate Random Forest, KNN, and SVM models
* Compare single-model performance with ensemble methods
* Implement a DBSCAN-based hybrid model
* Analyze results on multiple imbalanced data subsets
* Focus on fraud detection performance (fraud as positive class)

---

## Dataset

The dataset used is the **Credit Card Fraud Detection dataset** from Kaggle.

* Transactions made by European cardholders
* Features are anonymized using PCA
* Class label:

  * `0` → Non-fraud
  * `1` → Fraud (positive class)
* Extremely imbalanced (~0.17% fraud)

Dataset link:
[https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)

---

## Data Subsets

To follow the experimental setup of the reference paper, the dataset is divided into **three subsets** while keeping the fraud ratio consistent:

| Subset   | Fraud | Non-Fraud |
| -------- | ----- | --------- |
| Subset 1 | 100   | 10,000    |
| Subset 2 | 200   | 20,000    |
| Subset 3 | 300   | 30,000    |

Each subset is shuffled and split into training and testing sets.

---

## Models Used

The following classifiers are implemented:

* Random Forest (3 trees)
* K-Nearest Neighbors (k = 3)
* Support Vector Machine (RBF kernel)

Hyperparameters are kept simple to focus on **method comparison rather than tuning**.

---

## Experimental Setup

Two experiments are performed:

### Case Study 1 – Original Data

* Models are trained on the original dataset
* Predictions are combined using **majority voting**
* Individual models and ensemble performance are compared

### Case Study 2 – DBSCAN Hybrid Model

* DBSCAN is applied only to the training data
* Cluster labels are added as an extra feature
* Test samples are assigned a default cluster label
* Predictions are combined using **disjunctive (OR) voting**

---

## Evaluation Metrics

All results are reported for the **fraud class (1)**:

* Confusion matrix
* Precision
* Recall
* F1-score

---

## How to Run

1. Install dependencies:

```bash
pip install numpy pandas scikit-learn
```

2. Download `creditcard.csv` and place it in the project folder.

3. Run the provided scripts or notebook to generate subsets and evaluate models.

---

## Notes

* No random seed is fixed, so results may vary slightly between runs
* No resampling techniques (SMOTE, undersampling) are used
* The focus is on understanding ensemble behavior on imbalanced data

---

## Reference

Hybrid Ensemble Learning for Credit Card Fraud Detection
Scientific Reports, 2025

---
