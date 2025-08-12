```markdown
# Credit Risk Prediction: "Give Me Some Credit"

A machine learning project predicting the probability of borrowers experiencing financial distress within the next two years using the Kaggle "Give Me Some Credit" competition dataset.

## Project Overview

**Objective:** Build a model to predict serious financial delinquency (90+ days past due) in the next 2 years

**Dataset:** 250,000+ borrower records with 10 financial features

**Best Model:** AdaBoost Classifier achieving **0.857 AUC** on Kaggle test set

## Key Results

- **Kaggle Scores:** Public: 0.849 | Private: 0.857
- **Cross-Validation AUC:** 0.855
- **Model:** AdaBoost with SAMME algorithm
- **Data Challenge:** Highly imbalanced (6.7% default rate)

## Technical Approach

### Data Preprocessing
- Missing value imputation (median for income/dependents)
- Outlier capping at 99th percentile for extreme values
- Feature scaling using StandardScaler
- Removed 1 invalid record (age=0)

### Model Selection
Tested 9 algorithms using 5-fold cross-validation with AUC-ROC:
- Logistic Regression (baseline & balanced)
- Random Forest (baseline & balanced) 
- Decision Tree (baseline & balanced)
- Gaussian Naive Bayes
- K-Nearest Neighbors
- AdaBoost Classifier (selected)

### Evaluation Metrics
- **Primary:** AUC-ROC (appropriate for imbalanced binary classification)
- **Secondary:** Precision/Recall analysis via confusion matrices
- **Business Focus:** Ranking ability over raw accuracy

## Repository Structure

```
├── gimme_some_credit.ipynb    # Main Jupyter notebook with full analysis
├── submissions/
│   └── give_me_some_credit_submission.csv     # Kaggle submission file
├── README.md                    # Project documentation
└── requirements.txt             # Python dependencies
```

## Getting Started

### Prerequisites
```bash
pip install -r requirements.txt
```

### Running the Analysis
1. Clone the repository
2. Download data from [Kaggle Competition](https://www.kaggle.com/c/GiveMeSomeCredit)
3. Place `cs-training.csv` and `cs-test.csv` in a `data/` folder
4. Run `gimme_some_credit.ipynb`

## Key Learnings

- **AUC-ROC vs Accuracy:** For imbalanced datasets, accuracy is misleading - switched from 94% accuracy focus to 0.857 AUC
- **Feature Scaling Impact:** Essential for convergence in logistic regression
- **Outlier Treatment:** Financial data requires careful distinction between errors and legitimate extreme values
- **Business Metrics:** Confusion matrix analysis crucial for understanding real-world model impact

## Competition Performance

**Final Ranking:** Top tier performance with 0.857 private score demonstrating effective credit risk modeling suitable for real-world financial applications.

**Tags:** `machine-learning` `credit-risk` `kaggle` `binary-classification` `imbalanced-data` `adaboost` `python`
```
