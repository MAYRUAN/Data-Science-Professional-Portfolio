# National Childcare Cost & Regional Affordability Analysis

## Overview & Business Context
Childcare expenses represent a substantial financial burden for American working families, often rivaling or exceeding housing expenses. This project synthesizes the National Database of Childcare Prices (NDCP)—the most comprehensive federal repository of local childcare costs—to quantify regional affordability disparities across U.S. counties and evaluate county-level burdens against federal benchmarks.

## Analytical Pipeline & Technical Workflow
- Data Pipeline & Preprocessing: Utilized Python in JupyterLab to extract, clean, and standardize NDCP county-level records (2008–2018), harmonizing provider types (center-based vs. home-based), child age tiers (infant, toddler, preschool), and local economic variables (median household income, unemployment). 
- Benchmark Testing: Evaluated localized costs against the U.S. Department of Health and Human Services (HHS) 7% affordability benchmark to quantify annual household affordability deficits.
- Labor Force Correlation: Analyzed bivariate scatter relationships between weekly toddler care costs and female labor force participation across national and Texas county tiers.
- Multi-Medium Design Architecture: Applied a disciplined visual hierarchy (Navy Blue `#2C3E50` for stability, Action Orange `#D35400` and Critical Red for burden thresholds) across slides, infographics, and dashboard tools.

## Key Findings
- Cost Growth Decoupling (The Price Wedge): Between 2008 and 2017, weekly childcare costs grew 1.5x faster than family median income, creating a compounding cost-of-living gap.
- Federal Benchmark Breaches: While the federal safety limit recommendation is 7% of income, the average U.S. family spent 14.74% in 2018, Texas families averaged 13.71%, and Dallas County families spent 15.0% to 18.2% for center-based care (a critical burden).
- Regional DFW Uniformity: Weekly toddler center-based care costs were remarkably consistent across neighboring DFW counties—ranging from $163.55 in Dallas County to $171.15 in Tarrant County (a difference of under $8/week)—demonstrating that affordability hurdles are regionally systemic rather than isolated. 

## Repository Directory Structure

```text

│   ├── data/                  # NDCP data dictionaries and processed county aggregates
│   ├── scripts/               # Python data wrangling and exploratory analysis notebooks
│   ├── reports/               # Executive summary briefs and policy presentation slides
│   ├── requirements.txt       # Python environment dependencies
│   └── README.md              # Project documentation and summary
 

```

