# Credit Card Fraud Detection Under Extreme Class Imbalance

## Overview & Business Context
Credit card fraud introduces severe asymmetric costs in retail banking: undetected fraud results in direct chargeback write-offs, while false alarms trigger cardholder friction and costly manual reviews ($15+ per alert). This project investigates supervised machine learning pipelines for detecting unauthorized transactions in a highly imbalanced European cardholder dataset (0.17% fraud rate across 284,807 transactions).

## Methodology & Engineering Pipeline
- Preprocessing & Scaling: Standardized continuous features using RobustScaler to prevent outlier distortion. Converted raw elapsed 'Time' into cyclical 'Minute' (0–1440) and 'Hour' (0–24) behavioral features. Engineered amount transformation features ('Amount_log', 'Amount_to_mean_ratio') and dropped raw 'Time', establishing a 33-feature predictor matrix.
- Resampling Strategies: Evaluated Synthetic Minority Over-sampling Technique (SMOTE) across two training configurations: Full 1:1 balancing (227,451 synthetic frauds) and partial 20% sampling ratio (45,490 synthetic frauds).
- Partitioning: Utilized an 80/20 stratified train/test split (56,962 test records containing exactly 98 fraud cases) to ensure leak-free evaluation on real-world imbalance.
- Model Architectures: Benchmarked baseline Logistic Regression against cost-balanced Random Forest (100 estimators, class_weight='balanced').

## Key Results
- Baseline Logistic Regression (Full SMOTE): Achieved 0.90 recall (88/98 frauds intercepted) but generated 550 false alarms (precision = 0.14).
- Calibrated Logistic Regression (20% SMOTE): Maintained 0.89 recall (87/98 frauds intercepted) while reducing false positives from 550 to 134 (precision = 0.39).
- Cost-Balanced Random Forest: Achieved 0.95 precision with only 4 false alarms across 56,864 legitimate transactions, 0.73 recall (72/98 frauds caught), and an ROC-AUC of 0.963.
- Deployment Verdict: Random Forest is recommended for point-of-sale authorizations to minimize cardholder declines, with moderate scores routed to automated two-factor authentication (SMS/push OTP).

## Repository Directory Structure

```text

│   ├── data/                  # Schema documentation and data source reference
│   ├── notebooks/             # Reproducible Jupyter notebooks (EDA, SMOTE, Training)
│   ├── visualizations/        # Output plots (correlation matrix, scatter, distributions)
│   ├── requirements.txt       # Environment dependencies
│   └── README.md              # Project synopsis and execution guide
 

```
