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
└── README.md # This file
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
Open cell_count_analysis.ipynb

Run all cells (Cell → Run All)
             