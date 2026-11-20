# Consumer Loan Default Prediction and Analysis

## Overview & Business Context
Consumer loan underwriting introduces severe asymmetric costs for financial institutions: approving a high-risk borrower leads to direct credit losses from default, whereas rejecting a qualified applicant forfeits interest revenue and harms customer relationships. This project investigates supervised machine learning pipelines for identifying high-risk borrowers in an imbalanced consumer loan benchmark dataset (11.61% default rate across 255,347 borrower records). Because nominal accuracy (~88.5%) and default 0.50 probability cutoffs miss nearly 99% of defaults, this study pairs class-weighted ensemble modeling with post-processing decision-threshold tuning to balance loss prevention against approval access.

## Methodology & Engineering Pipeline
- Preprocessing & Feature Engineering: Normalized column headers to lowercase, verified zero missing values and zero duplicate rows, and dropped the non-predictive account identifier (`loanid`). Converted binary `Yes`/`No` indicators (`hasmortgage`, `hasdependents`, `hascosigner`) to `1`/`0` and applied one-hot encoding (`drop_first=True`) to multi-class categorical features (`education`, `employmenttype`, `maritalstatus`, `loanpurpose`), establishing a 24-feature predictor matrix.
- Exploratory Correlation & Risk Profiling: Confirmed near-zero multicollinearity ($\vert{}r\vert{} \le 0.01$) across continuous variables while identifying borrower age ($r = -0.17$), interest rate ($r = +0.13$), income ($r = -0.10$), employment tenure ($r = -0.10$), and employment status (unemployed ~13.6% vs. full-time ~9.5%) as primary risk drivers.
- Partitioning: Utilized an 80/20 stratified train/test split (204,277 training records and 51,070 test records containing 5,931 actual defaults and 45,139 non-defaults) to preserve the exact 11.61% default prevalence without synthetic distortion.
- Model Architectures & Threshold Tuning: Benchmarked an interpretable baseline Logistic Regression classifier (`max_iter=1000`) against a 200-tree cost-balanced Random Forest (`class_weight='balanced'`, `random_state=42`), followed by post-processing probability threshold evaluation across cutoffs of 0.50, 0.30, 0.25, and 0.20.

## Key Results
- Baseline Logistic Regression (0.50 Cutoff): Achieved 0.884 accuracy and an ROC-AUC of 0.730 (up from 0.719 on numeric-only predictors), but captured only 0.010 recall (57/5,931 defaults caught; F1-score = 0.020).
- Cost-Balanced Random Forest (Default 0.50 Cutoff): Achieved 0.885 accuracy and a higher ROC-AUC of 0.747, but caught only 91/5,931 defaults (recall = 0.015; F1-score = 0.030; precision = 0.734; 33 false rejections).
- Threshold-Tuned Random Forest (0.25 Operating Cutoff): Boosted default recall over 17-fold to 0.265 (1,569/5,931 defaults intercepted) and lifted the F1-score from 0.030 to 0.311 while maintaining practical precision (0.376) and capping false rejections at 5.8% (2,604/45,139 creditworthy applicants).
- Aggressive Threshold Comparison (0.20 Cutoff): Increased recall to 0.405 (2,401 defaults caught; F1-score = 0.358) but nearly doubled false rejections to 5,100 (11.3% of qualified borrowers).
- Deployment Verdict: Random Forest at the 0.25 cutoff is recommended as an early-warning screening filter in a two-tier underwriting workflow (routing flagged applications to manual review or adjusted terms rather than automatic denial), paired with Logistic Regression and SHAP reason codes for ECOA fair-lending governance.

## How to Run

### 1. Key Packages & Dependencies
The analysis and modeling pipeline requires Python 3.10+ and the following core libraries:
- pandas and numpy (data wrangling and array operations)
- scikit-learn (stratified splitting, one-hot encoding, Logistic Regression, Random Forest, and evaluation metrics)
- matplotlib and seaborn (histograms, boxplots, bar charts, correlation heatmap, ROC, and Precision-Recall curves)
- jupyterlab (interactive execution environment)

### 2. Execution Commands
To run the notebooks in an isolated, reproducible environment:

1. Clone the repository:
git clone https://github.com/MAYRUAN/Data-Science-Professional-Portfolio.git
cd Data-Science-Professional-Portfolio/10-Loan-Default-Prediction

2. Install package dependencies:
pip install -r requirements.txt

3. Launch JupyterLab:
jupyter lab

### 3. Clean Environment Verification
This notebook has been verified in a clean runtime environment. To reproduce all figures, metrics, and models without cached state, open `Loan-Default-Prediction-and-Analysis.ipynb` and select Kernel > Restart Kernel and Run All Cells to execute the pipeline sequentially.

## Repository Directory Structure

```text
10-Loan-Default-Prediction/
├── Loan-Default-Prediction-and-Analysis.ipynb   # Reproducible Jupyter notebook (EDA, Modeling, Threshold Tuning)
└── README.md                                    # Project synopsis and execution guide
