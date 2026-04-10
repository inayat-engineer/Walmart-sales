# Walmart Sales Analysis (Python + SQL)

## Overview
This repository contains a practical Walmart sales analysis workflow built in a Jupyter notebook.
The project:
- loads raw sales data from `Walmart.csv`
- performs basic data quality checks and cleaning
- engineers a `total` sales column
- exports cleaned data to `Walmart_clean_data.csv`
- loads the cleaned dataset into MySQL for SQL-based analysis

Core implementation lives in:
- `project.ipynb`

## Dataset
- Raw dataset: `Walmart.csv`
- Cleaned output: `Walmart_clean_data.csv`

## Prerequisites
- Python 3.8+
- Jupyter Notebook (or JupyterLab)
- MySQL server (if you want to run the SQL load step)

## Installation
From the repository root:

```bash
pip install -r requirements.txt
```

> Note: the notebook uses MySQL via SQLAlchemy + PyMySQL.

## How to Run
1. Open the repository root:
   ```bash
   cd Walmart-sales
   ```
2. Start Jupyter:
   ```bash
   jupyter notebook
   ```
3. Open `project.ipynb` and run cells in order.

## Notebook Workflow Summary
`project.ipynb` follows this sequence:
1. Import libraries (`pandas`, `os`, SQL connectors)
2. Read Walmart sales CSV into a DataFrame
3. Explore schema and quality (`head`, `describe`, `info`)
4. Remove duplicates and null rows
5. Convert `unit_price` from currency-formatted text to float
6. Create `total = unit_price * quantity`
7. Save cleaned data to `Walmart_clean_data.csv`
8. Create a MySQL engine and write data using `DataFrame.to_sql`

## Database Configuration Notes
The notebook includes a MySQL engine example in code. Before running DB cells, update connection details for your environment:
- username
- password
- host/port
- database name

If MySQL is not available, you can still run all cleaning and CSV export steps.

## Repository Structure
```text
.
├── README.md
├── requirements.txt
├── project.ipynb
├── Walmart.csv
└── Walmart_clean_data.csv
```

## Current Testing / Linting Status
This repository currently does not include a configured automated test suite or lint configuration.
Validation is performed by running notebook cells and verifying generated outputs/files.
