# Major League Baseball Attendance Drivers & Promotional ROI Modeling

## Overview & Business Context
Major League Baseball franchises rely heavily on game-day ticket, concession, and merchandise revenue, yet stadium attendance fluctuates sharply across scheduling windows, opposing teams, weather conditions, and promotional campaigns. Because giveaway items, fireworks nights, and targeted marketing carry substantial upfront operational costs, sports marketing and revenue operations teams need empirical evidence to separate genuine promotional lift from baseline calendar demand. This project analyzes 81 Los Angeles Dodgers home games to quantify attendance drivers and isolate the net attendance impact of stadium promotions.

## Methodology & Engineering Pipeline
- Data Wrangling & Feature Engineering: Standardized 81 game-level records (`dodgers-2022.csv`), converting categorical scheduling variables (`month`, `day_of_week`, `opponent`), weather conditions (`skies`, `temp`), and binary promotional flags (`cap`, `shirt`, `fireworks`, `bobblehead`) into model-ready predictors.
- Exploratory & Statistical Analysis: Evaluated attendance distributions across days of the week, months, game times (`day_night`), and promotional events using grouped summary statistics, boxplots, and correlation diagnostics.
- Predictive & Promotional Lift Modeling: Trained and compared regression models (OLS Linear Regression and tree-based/regularized baselines) to estimate expected game attendance and isolate the marginal ticket lift attributable to specific promotional campaigns while controlling for opponent and calendar effects.
- Visual Diagnostics & Revenue Strategy: Generated executive comparison charts (`matplotlib` and `seaborn`) highlighting promotional ROI, weekday vs. weekend baseline shifts, and optimal giveaway deployment windows.

## Key Results
- High-Impact Promotional Lift: Bobblehead giveaways generated the strongest marginal attendance boost among all promotional levers, whereas lower-cost giveaways (such as caps and shirts) produced smaller or schedule-dependent lift once day-of-week effects were controlled.
- Calendar & Scheduling Baseline Effects: Game-day timing (`day_of_week` and `month`) and opponent draw accounted for substantial baseline variance—demonstrating that deploying high-cost promotions on mid-week games yields higher incremental ticket ROI than saturating already high-demand weekend matchups.
- Actionable Marketing Verdict: Provided a data-driven promotional allocation framework recommending targeted bobblehead and fireworks scheduling on lower-baseline weekday dates to maximize incremental stadium utilization and net game-day margin.

## How to Run

### 1. Key Packages & Dependencies
The analysis and modeling pipeline requires Python 3.10+ and the following core libraries:
- pandas and numpy (data cleaning, categorical encoding, and feature engineering)
- scikit-learn and statsmodels (regression modeling, statistical inference, and error evaluation)
- matplotlib and seaborn (exploratory boxplots, promotional lift comparisons, and diagnostic plots)
- jupyterlab (interactive execution environment)

### 2. Execution Commands
To run the notebooks in an isolated, reproducible environment:

1. Clone the repository:
git clone https://github.com/MAYRUAN/Data-Science-Professional-Portfolio.git
cd Data-Science-Professional-Portfolio

2. Install package dependencies:
pip install -r requirements.txt

3. Launch JupyterLab:
jupyter lab

### 3. Clean Environment Verification
This notebook has been verified in a clean runtime environment. To reproduce all figures, metrics, and models without cached state, open the notebook and select Kernel > Restart Kernel and Run All Cells to execute the pipeline sequentially.

## Repository Directory Structure

```text
08-mlb-attendance-roi-modeling/
├── README.md                            # Project documentation, methodology, and key findings
└── mlb-attendance-roi-modeling.ipynb    # Reproducible Jupyter notebook (EDA, Regression & Promotional ROI Modeling)

```
