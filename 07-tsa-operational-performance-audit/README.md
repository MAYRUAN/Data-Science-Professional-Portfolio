# TSA Operational Performance & Passenger Friction Audit

## Overview & Business Context
Aviation regulators and airport operations leaders rely on passenger complaint logs to monitor checkpoint screening quality, customer experience, and procedural compliance across U.S. airports. However, raw complaint counts distort operational risk because high-traffic hubs naturally generate higher incident volume than regional airports. This project integrates four relational TSA complaint and airport reference tables to clean, geocode, and scale-normalize multi-year passenger complaint data—isolating true operational bottlenecks by airport hub, complaint category, and subcategory.

## Methodology & Engineering Pipeline
- Multi-Table Relational Integration: Joined four structured TSA datasets (`airport`, `category`, `subcategory`, and `icao`) to link incident records with standardized airport identifiers, geographic coordinates, and hierarchical complaint taxonomies.
- Data Standardization & Text Cleaning: Normalized airport codes, resolved missing or malformed geographic entries, and standardized suppressed/asterisked subcategory labels for consistent aggregation.
- Scale-Normalized Risk Benchmarking: Evaluated raw complaint volume alongside passenger throughput/hub scale to distinguish systemic screening friction from high-volume hub effects.
- Visual Storytelling & Diagnostic Design: Built six targeted visualizations in Python (`matplotlib`, `seaborn`, and `plotly`) applying Tufte's high data-ink ratio and Gestalt grouping principles—including small multiples, ranked category/subcategory breakdowns, and geospatial airport maps.

## Key Results
- High-Friction Complaint Concentration: Isolated dominant complaint categories and granular subcategories (such as screening delays, property handling, and screening procedures) driving the majority of passenger escalations.
- Hub Volume vs. Operational Efficiency: Demonstrated that raw incident rankings disproportionately penalize major international hubs, whereas scale-normalized metrics pinpoint specific regional and mid-tier airports requiring targeted staffing or workflow intervention.
- Actionable Operational Intervention: Translated multi-dimensional visual diagnostics into an executive call to action focused on checkpoint queue management, targeted officer retraining, and standardized incident logging.

## How to Run

### 1. Key Packages & Dependencies
The analysis and visualization pipeline requires Python 3.10+ and the following core libraries:
- pandas and numpy (relational table joins, text cleaning, and scale normalization)
- matplotlib, seaborn, and plotly (small multiples, ranked bar charts, and geospatial airport mapping)
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
07-tsa-operational-performance-audit/
├── README.md                                  # Project documentation, methodology, and key findings
└── tsa-operational-performance-audit.ipynb    # Reproducible Jupyter notebook (Relational Joins, Visual Analytics & Audit)
```
