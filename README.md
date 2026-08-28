# Password Strength Classification Using Machine Learning and Structural Features

## Overview

This project investigates the effectiveness of machine learning techniques for classifying password strength using structural characteristics extracted from password strings.

The study combines two publicly available password datasets and applies data cleaning, deduplication, password strength labeling, feature engineering, machine learning model training, hyperparameter tuning, ensemble learning, and comprehensive model evaluation.

After preprocessing and deduplication, the final dataset contains **3,590,654 unique passwords**.

Password strength labels are generated using **zxcvbn** and converted into two categories: **Weak** and **Strong**.

The study evaluates multiple machine learning approaches and compares their predictive performance using conventional classification metrics, statistical testing, error analysis, feature importance analysis, and computational evaluation.

---

## Research Workflow

```text
Password Datasets
       │
       ▼
Data Cleaning and Deduplication
       │
       ▼
3,590,654 Unique Passwords
       │
       ▼
Password Strength Labeling
(zxcvbn)
       │
       ▼
Weak / Strong Classification
       │
       ▼
Feature Engineering
       │
       ▼
Train / Validation / Test Split
       │
       ▼
Feature Scaling and Training-Set Balancing
       │
       ▼
Baseline Model Training
       │
       ▼
Hyperparameter Tuning
       │
       ▼
Stacking Ensemble Development
       │
       ▼
Final Test Evaluation
       │
       ▼
Statistical and Interpretability Analysis
```

---

## Dataset

This study uses two publicly available password datasets obtained from Kaggle:

- **Leaked Passwords Largest Datasets**
- **Ultimate Cybersecurity Password & Username Dataset**

The datasets were combined and processed through data cleaning and deduplication procedures.

### Final Dataset

| Dataset Property | Value |
|---|---:|
| Final number of unique passwords | 3,590,654 |
| Password representation | Raw password strings |
| Classification task | Binary classification |
| Target classes | Weak and Strong |

---

## Password Strength Labeling

Password strength was evaluated using the **zxcvbn** password strength estimator.

The generated strength scores were converted into binary categories:

| Category | Label |
|---|---:|
| Weak | 0 |
| Strong | 1 |

The resulting classification task evaluates how effectively machine learning models can learn **zxcvbn-derived password strength categories** from structural password characteristics.

---

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

These features represent different aspects of password structure, character composition, repetition, and complexity.

---

## Machine Learning Models

The following models were evaluated:

- Logistic Regression
- Linear Support Vector Machine
- Decision Tree
- Random Forest
- Neural Network
- Stacking Ensemble

### Final Stacking Ensemble

The final ensemble combines the following base learners:

- Logistic Regression
- Random Forest
- Neural Network

A **Logistic Regression model** is used as the meta-learner.

The ensemble uses probability-based stacking, where predictions from the base models are used as inputs to the meta-learner.

---

## Model Evaluation

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- Log Loss

Additional analyses include:

- McNemar's statistical test
- Classification error analysis
- Class-wise performance analysis
- Random Forest feature importance
- Permutation feature importance
- Computational efficiency evaluation

---

## Key Findings

The experimental results indicate that structural password characteristics can effectively support the classification of **zxcvbn-derived Weak and Strong password categories**.

The **Stacking Ensemble** achieved the strongest overall performance among the evaluated approaches.

Key observations include:

- The Stacking Ensemble provided the strongest overall classification performance.
- Nonlinear and ensemble-based approaches captured relationships between structural password characteristics more effectively than simpler models.
- Password length was identified as the most influential feature within the engineered feature set.
- The results represent agreement with the adopted zxcvbn-based labeling framework and should not be interpreted as a direct measurement of real-world password crackability.

---

## Project Structure

```text
Password-Strength-Classification-Using-Structural-Features/
│
├── 2023-3-60-043_CSE487_Source_Code.ipynb
│
├── README.md
│
└── .gitignore
```

---

## Technologies and Libraries

The project was developed using Python and the following libraries:

- Python
- Pandas
- NumPy
- Scikit-learn
- zxcvbn
- Matplotlib
- SciPy

---

## Reproducibility

The Jupyter Notebook contains the main experimental workflow, including:

1. Dataset loading
2. Data cleaning
3. Data quality checks
4. Password labeling
5. Feature engineering
6. Data splitting
7. Feature scaling
8. Training-set balancing
9. Baseline model training
10. Hyperparameter tuning
11. Stacking ensemble development
12. Final test evaluation
13. Statistical comparison
14. Error analysis
15. Feature importance analysis

---

## Limitations

The results of this study should be interpreted within the scope of the adopted methodology.

- Password strength labels depend on the zxcvbn framework.
- Binary Weak/Strong classification reduces the granularity of password strength levels.
- Structural features do not fully capture dictionary words, semantic patterns, or other contextual characteristics.
- The study does not directly evaluate password resistance using real password-cracking attacks.
- Generalization may be limited across different languages, populations, and password-generation behaviors.

---

## Future Work

Future research may explore:

- Validation using real-world password-cracking experiments
- Dictionary and semantic password features
- Keyboard-pattern analysis
- Multilingual password analysis
- Multiclass password strength prediction
- External dataset validation
- Privacy-preserving approaches to password strength analysis

---

## Disclaimer

This project is intended for academic and research purposes. The password strength predictions produced by the models represent classifications based on the adopted **zxcvbn-derived labeling framework** and structural password features. They should not be considered a direct measurement of real-world password crackability or security against all attack methods.
