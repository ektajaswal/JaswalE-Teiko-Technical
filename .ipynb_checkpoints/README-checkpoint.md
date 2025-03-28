# Immune Cell Population Analysis

## Project Overview
This project analyzes immune cell population data from patient samples, comparing responders and non-responders to treatment tr1 in melanoma patients. The analysis includes:
- Conversion of absolute cell counts to relative frequencies
- Statistical comparison of cell populations between responders and non-responders
- Database schema design for large-scale data storage
- Example SQL queries for common analyses

## Files Included
/project-root/
├── data/
│ └── cell-count.csv # Raw input data
├── outputs/
│ ├── cell-count-relative-freq.csv # Processed frequencies
│ ├── significant_populations.csv # Stats results (p-values)
│ └── *.png # Boxplot images (5 files)
├── cell_analysis.ipynb # Main analysis notebook
└── README.md 
## Requirements
- Python 3.7+
- Jupyter Notebook
- Required packages: pandas, numpy, matplotlib, seaborn, scipy

## Installation
1. Clone this repository
2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   venv\Scripts\activate    # Windows
3. Install dependencies:
             pip install pandas numpy matplotlib seaborn scipy
Running the Analysis
Start Jupyter Notebook:

bash
Copy
jupyter notebook
Open cell_analysis.ipynb

Run all cells (Cell → Run All)

Output Files
cell-count-relative-freq.csv: Relative frequencies for each cell population

significant_populations.csv: Statistical results of response comparisons

Boxplot images (one per cell population):

b_cell_response_comparison.png

cd8_t_cell_response_comparison.png

cd4_t_cell_response_comparison.png

nk_cell_response_comparison.png

monocyte_response_comparison.png

Key Findings
Based on the analysis, these cell populations showed significant differences (p < 0.05) between responders and non-responders:

Population	Responder Mean	Non-responder Mean	p-value
cd4_t_cell	36.33%	26.33%	0.008
monocyte	8.00%	22.67%	0.034
Database Schema Design
The proposed database includes 7 tables to efficiently store and query this data:

Projects: Research project information

Subjects: Patient demographic data

Treatments: Treatment protocols

Samples: Biological sample information

Cell_Populations: Immune cell type definitions

Cell_Counts: Measurement data

Treatment_Response: Clinical outcomes

Example Queries
Count subjects per condition:
SELECT condition, COUNT(DISTINCT subject_id) as subject_count
FROM Subjects
GROUP BY condition;
Find melanoma PBMC samples at baseline (time=0) with tr1 treatment:

                                                  
             