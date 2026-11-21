# Netflix Global Top 10 Viewership & Content Investment Strategy

## Overview & Business Context
Global streaming platforms face intense capital allocation trade-offs when commissioning original programming and licensing regional titles: high-budget English blockbusters drive immediate subscriber acquisition spikes, whereas localized non-English series sustain long-term retention across international territories. This project evaluates multi-year global streaming performance across three official Netflix Top 10 datasets (Global Weekly, Country-Level Weekly, and All-Time Most Popular) to uncover engagement drivers and guide content investment and release scheduling decisions.

## Methodology & Engineering Pipeline
- Multi-Source Data Integration & Cleaning: Consolidated and standardized three distinct Netflix Top 10 tables (Global, Country-level, and Most Popular), normalizing weekly ranking timestamps, title identifiers, runtime durations, and cumulative viewing hours across English and Non-English film and TV categories.
- Engagement & Retention Metric Engineering: Computed cumulative weekly viewership velocity, consecutive weeks-in-Top-10 longevity scores, and regional market penetration rates to separate short-term release spikes from sustained audience retention.
- Cross-Market & Geospatial Visualization: Built comparative distribution plots, temporal release trend lines, and geospatial market heatmaps using Python (`pandas`, `matplotlib`, `seaborn`) to benchmark domestic versus international content performance.

## Key Results
- Dual-Engine Viewership Model: Uncovered a clear structural split between high-velocity blockbuster releases (generating 250M+ views within their opening window) and localized high-retention titles (sustaining 20–30 consecutive weeks in regional Top 10 charts).
- Non-English Retention Advantage: Demonstrated that non-English television series achieve disproportionately longer chart longevity in local and neighboring regional markets compared to single-week blockbuster spikes.
- Strategic Investment & Scheduling Verdict: Recommended balancing tentpole English release windows around peak seasonal viewing periods with targeted regional production investments in high-retention local markets to maximize subscriber lifetime value and minimize post-release churn.

## How to Run

### 1. Key Packages & Dependencies
The analysis and visualization pipeline requires Python 3.10+ and the following core libraries:
- pandas and numpy (multi-table data wrangling, aggregation, and temporal alignment)
- matplotlib and seaborn (trend visualizations, distribution charts, and geospatial market plots)
- jupyterlab (interactive execution environment)

### 2. Execution Commands
To run the notebook in an isolated, reproducible environment:

1. Clone the repository:
git clone https://github.com/MAYRUAN/Data-Science-Professional-Portfolio.git
cd Data-Science-Professional-Portfolio/04-netflix-global-top10-strategy

2. Install package dependencies:
pip install -r requirements.txt

3. Launch JupyterLab:
jupyter lab

### 3. Clean Environment Verification
This notebook has been verified in a clean runtime environment. To reproduce all figures and summary metrics without cached state, open `netflix-global-top10-strategy.ipynb` and select Kernel > Restart Kernel and Run All Cells to execute the pipeline sequentially.

## Repository Directory Structure

```text
04-netflix-global-top10-strategy/
├── README.md                              # Project synopsis, key findings, and execution guide
└── netflix-global-top10-strategy.ipynb    # Reproducible Jupyter notebook (EDA, Retention & Geospatial Analysis)
