# S&P 500 Multi-Source Financial Database Integration & Market Visualizations

## Overview & Business Context
Equity analysts and portfolio managers rely on disparate financial data sources—including structured flat files, public market encyclopedias, and live financial APIs—to evaluate sector concentration, valuation multiples, and historical price momentum across S&P 500 companies. Because raw sources vary in ticker formatting, schema structure, and update frequency, consolidating them into a governed relational warehouse is critical for reproducible market reporting. This project builds an end-to-end ETL and visualization pipeline that extracts, cleans, and integrates three distinct S&P 500 datasets into a SQLite database, delivering unified SQL analytics and executive-ready financial charts.

## Methodology & Engineering Pipeline
- Multi-Source Extraction & Ingestion: Collected and standardized S&P 500 constituent metadata, valuation fundamentals, and historical market pricing across three complementary sources (CSV flat files, HTML web scraping, and financial API endpoints).
- Schema Normalization & Entity Resolution: Standardized ticker symbols (e.g., resolving class-share delimiters such as `BRK.B` vs. `BRK-B`), parsed numeric currency/percentage strings, handled missing fundamental fields, and deduplicated constituent records.
- Relational SQLite Warehouse Design: Loaded cleaned tables into a normalized SQLite database with primary/foreign key alignment on ticker symbols, executing multi-table SQL joins and aggregations to produce a unified analytics-ready master table.
- Financial Visualizations & Executive Reporting: Built targeted market visualizations in Python (`matplotlib` and `seaborn`) examining GICS sector market-cap weightings, valuation distributions (P/E and dividend yield), and comparative price-return performance.

## Key Results
- Unified Relational Financial Warehouse: Successfully consolidated three heterogeneous data feeds into a single queryable SQLite database, eliminating ticker mismatches and manual spreadsheet reconciliation.
- Sector Concentration & Valuation Insights: Quantified market capitalization concentration and valuation dispersion across S&P 500 sectors, highlighting stark differences between high-growth technology leaders and defensive dividend-paying sectors.
- Reproducible Reporting Deliverables: Generated clean summary tables and publication-grade visual diagnostics ready for investment committee or portfolio review workflows.

## How to Run

### 1. Key Packages & Dependencies
The ETL, database, and visualization pipeline requires Python 3.10+ and the following core libraries:
- pandas and numpy (data cleaning, ticker standardization, and fundamental metric calculations)
- sqlite3 and sqlalchemy (relational database creation, schema management, and SQL joins)
- requests, BeautifulSoup4, and yfinance (web table extraction and market API ingestion)
- matplotlib and seaborn (sector breakdown, valuation distribution, and return visualizations)
- JupyterLab (interactive execution environment)
  
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
This notebook has been verified in a clean runtime environment. To reproduce all tables, database queries, and figures without cached state, open the notebook, select Kernel > Restart Kernel, then Run All Cells to execute the pipeline sequentially.

## Repository Directory Structure

```text
09-sp500-financial-data-visualizations/
├── README.md                                  # Project documentation, methodology, and key findings
└── sp500-financial-data-visualizations.ipynb  # Reproducible Jupyter notebook (Multi-Source ETL, SQLite & Visualizations)

```
