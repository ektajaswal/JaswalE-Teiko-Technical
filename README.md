# Immune Cell Population Analysis

```python
# Project Overview
"""
This project analyzes immune cell population data from patient samples, comparing responders 
and non-responders to treatment tr1 in melanoma patients. The analysis includes:
- Conversion of absolute cell counts to relative frequencies
- Statistical comparison of cell populations
- Database schema design for large-scale data storage
- Example SQL queries for common analyses
"""
# Files Structure
# /project-root/
# ├── data/
# │   └── cell-count.csv               # Raw input data
# ├── outputs/
# │   ├── cell-count-relative-freq.csv # Processed frequencies
# │   ├── significant_populations.csv  # Stats results
# │   └── *.png                       # Boxplot images
# ├── cell_analysis.ipynb             # Main notebook
# └── README.md                       # This file
# Requirements
requirements = [
    "Python 3.7+",
    "Jupyter Notebook",
    "pandas",
    "numpy", 
    "matplotlib",
    "seaborn",
    "scipy"
]
# Installation
# 1. Clone repository:
git clone https://github.com/ektajaswal/JaswalE-Teiko-Technical.git
cd JaswalE-Teiko-Technical

# 2. Create virtual environment:
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate    # Windows

# 3. Install packages:
pip install pandas numpy matplotlib seaborn scipy
# Running the Analysis
"""
1. Start Jupyter: jupyter notebook
2. Open cell_analysis.ipynb
3. Run all cells (Cell > Run All)
"""
# Key Findings
import pandas as pd

results = pd.DataFrame({
    'Population': ['cd4_t_cell', 'monocyte'],
    'Responder Mean': [36.33, 8.00],
    'Non-responder Mean': [26.33, 22.67], 
    'p-value': [0.008, 0.034]
})
print(results.to_markdown(index=False))
-- Database Schema
CREATE TABLE projects (
    project_id VARCHAR(20) PRIMARY KEY,
    project_name VARCHAR(100),
    description TEXT
);

CREATE TABLE subjects (
    subject_id VARCHAR(20) PRIMARY KEY,
    project_id VARCHAR(20) REFERENCES projects(project_id),
    condition VARCHAR(50),
    age INTEGER,
    sex CHAR(1)
);
-- Example Queries
-- 1. Count subjects per condition
SELECT condition, COUNT(*) as subject_count 
FROM subjects
GROUP BY condition;

-- 2. Find melanoma PBMC samples
SELECT s.sample_id
FROM samples s
JOIN subjects sub ON s.subject_id = sub.subject_id
WHERE sub.condition = 'melanoma'
  AND s.sample_type = 'PBMC';
