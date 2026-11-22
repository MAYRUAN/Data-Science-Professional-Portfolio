# U.S. Vehicle Theft Epidemic & Multi-City Trend Modeling

## Overview & Business Context
Auto insurers, fleet operators, and municipal law enforcement agencies face rising financial losses from localized surges in motor vehicle theft. Because theft rates vary sharply across state jurisdictions, seasonal cycles, and vehicle segments, reactive resource allocation often lags emerging hotspots. This project analyzes multi-year U.S. vehicle theft records and applies time-series trend decomposition and predictive modeling to forecast theft trajectories and identify high-risk geographic and temporal patterns.

## Methodology & Engineering Pipeline
- Data Wrangling & Normalization: Cleaned and standardized multi-state motor vehicle theft records, resolving missing entries, aligning date indices, and normalizing raw incident counts against regional baselines for valid cross-state comparisons.
- Exploratory & Temporal Feature Engineering: Extracted year, month, seasonality indicators, rolling averages, and year-over-year growth rates to isolate structural shifts from routine seasonal fluctuations.
- Predictive & Trend Modeling: Evaluated regression and time-series forecasting baselines to project near-term theft volume trajectories and quantify key regional risk drivers.
- Geospatial & Diagnostic Visualization: Generated state-level comparison charts, seasonal trend lines, and forecast residual diagnostics using `matplotlib` and `seaborn`.

## Key Results
- Pronounced Seasonal & Regional Concentration: Uncovered recurring late-summer and autumn theft peaks alongside sharp state-level disparities, demonstrating that raw incident volume without population/fleet normalization distorts regional risk rankings.
- Structural Trend Shifts: Identified multi-year inflection points where specific jurisdictions experienced accelerated theft growth compared to national baselines.
- Risk & Underwriting Verdict: Demonstrated how normalized time-series forecasting supports dynamic regional pricing adjustments, targeted anti-theft incentives, and proactive law enforcement resource deployment.

## How to Run

### 1. Key Packages & Dependencies
This analysis is written in **R (4.2+)** and requires the **IRkernel** (if running inside JupyterLab) or **RStudio**, along with the following CRAN packages:
- `tidyverse` (`dplyr`, `tidyr`, `ggplot2` for data wrangling and visual storytelling)
- `treemapify` (proportional treemap visualizations)
- `scales` (percentage and axis number formatting)

### 2. Installation & Execution Commands
To run the notebooks in an isolated, reproducible environment:

1. Clone the repository:
git clone https://github.com/MAYRUAN/Data-Science-Professional-Portfolio.git
cd Data-Science-Professional-Portfolio/06-us-vehicle-theft-trend-modeling


2. Install required R packages (in an R console or RStudio): 
install.packages(c("tidyverse", "treemapify", "scales"))

3. Launch JupyterLab:
jupyter lab

### 3. Clean Environment Verification
This notebook has been verified in a clean runtime environment. To reproduce all figures, metrics, and models without cached state, open the notebook, ensure the R kernel is selected in the top-right corner, select Kernel > Restart Kernel, then Run All Cells to execute the pipeline sequentially.

## Repository Directory Structure

```text
06-us-vehicle-theft-trend-modeling/
├── README.md                                # Project documentation, methodology, and key findings
└── us-vehicle-theft-trend-modeling.ipynb    # Reproducible Jupyter notebook (EDA, Trend Decomposition & Forecasting)

```
