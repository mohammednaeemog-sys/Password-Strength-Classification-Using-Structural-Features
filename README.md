# Password Strength Classification Using Structural Features

This project investigates machine learning approaches for classifying passwords into Weak and Strong categories using structural password characteristics.

## Dataset

Two publicly available password datasets were used:

- Leaked Passwords Largest Datasets
- Ultimate Cybersecurity Password & Username Dataset

After data cleaning and deduplication, the final dataset contained **3,590,654 unique passwords**.

## Feature Engineering

Eight structural features were extracted from each password:

1. Password Length
2. Digit Count
3. Lowercase Count
4. Uppercase Count
5. Special Character Count
6. Repeated Character Count
7. Maximum Consecutive Characters
8. Character-Type Transitions

## Password Labeling

Password strength was evaluated using **zxcvbn** and converted into two categories:

- Weak
- Strong

## Machine Learning Models

The following models were evaluated:

- Logistic Regression
- Linear Support Vector Machine
- Decision Tree
- Random Forest
- Neural Network
- Stacking Ensemble

The final Stacking Ensemble used Logistic Regression, Random Forest, and Neural Network as base learners, with Logistic Regression as the meta-learner.

## Evaluation Metrics

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- Log Loss

## Key Findings

The Stacking Ensemble achieved the strongest overall performance. The study also included statistical comparison, classification error analysis, feature importance analysis, and computational efficiency evaluation.

Password length was identified as the most influential feature within the engineered feature set.

## Project Structure

```text
.
├── 2023-3-60-043_CSE487_...ipynb
├── README.md
└── .gitignore
