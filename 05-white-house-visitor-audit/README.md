# White House Visitor Log Governance & Access Audit

## Overview & Business Context
Public-sector access logs and high-security facility registries require rigorous data hygiene, entity standardization, and anomaly screening to support institutional transparency, compliance auditing, and operational security. Because raw visitor logs contain inconsistent name formatting, unstandardized timestamps, and high-frequency recurring entries, manual review cannot reliably distinguish routine staff or public tour traffic from high-frequency executive meetings. This project builds an automated Python auditing and exploratory analytics pipeline to clean, standardize, and profile White House visitor log records.

## Methodology & Engineering Pipeline
- Schema Standardization & String Normalization: Audited raw visitor log fields, standardized column naming conventions, stripped whitespace, and normalized inconsistent capitalization across visitor names, visitee identifiers, and meeting locations.
- Temporal Parsing & Feature Engineering: Converted raw appointment and arrival/departure strings into structured datetime objects, extracting appointment lead times, meeting durations, day-of-week patterns, and monthly access volume trends.
- Entity Frequency & Anomaly Profiling: Aggregated high-frequency visitors, top host officials, and recurring group visits to separate routine public tour traffic from concentrated executive or policy-level engagements.
- Exploratory Governance Visualizations: Generated distribution charts, temporal volume trends, and top-entity rankings using `matplotlib` and `seaborn` to communicate audit findings for compliance and oversight review.

## Key Results
- Data Quality & Entity Resolution: Eliminated duplicate and malformed log entries while standardizing visitor and host naming variations, establishing a reliable audit baseline for downstream aggregation.
- Access Concentration & Seasonal Cadence: Identified clear weekday and seasonal spikes in visitor traffic, distinguishing broad public tour waves from smaller, high-frequency executive office appointments.
- Governance & Audit Verdict: Demonstrated how automated entity normalization and temporal anomaly checks streamline compliance reviews and flag unusual access patterns for targeted oversight.

## How to Run

### 1. Key Packages & Dependencies
The auditing and exploratory analysis pipeline requires Python 3.10+ and the following core libraries:
- pandas and numpy (data cleaning, string normalization, and datetime feature engineering)
- matplotlib and seaborn (temporal trend charts, frequency distributions, and audit visuals)
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
This notebook has been verified in a clean runtime environment. To reproduce all figures and audit summaries without cached state, open the notebook and select Kernel > Restart Kernel and Run All Cells to execute the pipeline sequentially.

## Repository Directory Structure

```text
05-white-house-visitor-audit/
├── README.md                            # Project documentation, methodology, and key findings
└── white-house-visitor-audit.ipynb      # Reproducible Jupyter notebook (Data Hygiene, Entity Resolution & Audit EDA)

```
