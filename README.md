# Data Science Professional Portfolio
Technical Repository Layer

**Author:** Chunmei Ruan | Principal Data Analyst & Data Science Graduate Student  
**Presentation Layer (GitHub Pages):** [https://mayruan.github.io/Data-Science-Professional-Portfolio/](https://mayruan.github.io/Data-Science-Professional-Portfolio/)  
**LinkedIn:** [https://www.linkedin.com/in/chunmei-ruan/](https://www.linkedin.com/in/chunmei-ruan/)

---

## Architecture Overview: Technical Repository Layer
This repository serves as the **Technical Repository Layer** of a two-tier data science portfolio architecture:

- **Presentation Layer (GitHub Pages):** An executive-facing visual storefront (`index.html`) summarizing business problems, analytical methodologies, and quantified business impact for rapid recruiter and hiring-manager review.
- **Technical Repository Layer (This Repository):** A governed, reproducible codebase housing end-to-end Jupyter notebooks, ETL pipelines, database schemas, Dockerized big data configurations, and project-level documentation (`README.md`) that bridge high-level business outcomes directly to verifiable technical implementations.

---

## How to Run

### 1. Key Packages & Dependencies
The repository-wide analytics, machine learning, and data engineering pipelines require Python 3.10+ and the following core libraries defined in `requirements.txt`:
- pandas, numpy, and scipy (data wrangling, array operations, and statistical diagnostics)
- scikit-learn, imbalanced-learn, and statsmodels (stratified splitting, feature encoding, SMOTE resampling, classification/regression modeling, and evaluation metrics)
- matplotlib, seaborn, and plotly (statistical charts, correlation heatmaps, ROC/Precision-Recall curves, and interactive geospatial visualizations)
- requests, beautifulsoup4, lxml, sqlalchemy, and yfinance (web scraping, API ingestion, and SQLite relational warehouse integration)
- jupyterlab (interactive execution environment; Project 02 runs in a Dockerized Hadoop/Spark cluster environment)

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
All notebooks featured in the repository have been verified in a clean runtime environment. To reproduce all figures, metrics, and models without cached state, open any target `.ipynb` notebook and select Kernel > Restart Kernel, then Run All Cells to execute the pipeline sequentially.


## Repository Directory & Project Index

```text
Data-Science-Professional-Portfolio/
├── index.html                                         # Presentation Layer storefront (GitHub Pages)
├── requirements.txt                                   # Centralized Python dependency manifest
├── README.md                                          # Technical Repository Layer architecture & setup guide
├── 01-credit-card-fraud-detection/                    # Supervised ML & SMOTE class-imbalance mitigation
├── 02-distributed-big-data-fraud-pipeline/            # Dockerized Hadoop/Spark/NiFi/Hive/HBase pipeline on GCP
├── 03-national-childcare-affordability/               # County-level HHS 7% affordability benchmark & Tableau storytelling
├── 04-netflix-global-top10-strategy/                  # Multi-market streaming engagement & retention analytics
├── 05-white-house-visitor-audit/                      # 398,210-record federal access log consolidation & bottleneck audit
├── 06-us-vehicle-theft-trend-modeling/                # Longitudinal multi-city crime trend modeling (2019–2022)
├── 07-tsa-operational-performance-audit/              # 780,000+ record relational audit & scale-normalized diagnostics
├── 08-mlb-attendance-roi-modeling/                    # Econometric OLS regression & promotional lift ROI modeling
├── 09-sp500-financial-data-visualizations/            # Multi-source ETL (CSV, Web, API) into SQLite warehouse
└── 10-loan-default-prediction-and-analysis/           # Random Forest (ROC-AUC 0.747) & 0.25 threshold optimization

```
