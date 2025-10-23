#  DSA2040A_ET_Exam_-Victor-_-388-  
*A Complete Data Extraction, Cleaning, Transformation, and Load Pipeline*

![GitHub repo size](https://img.shields.io/github/repo-size/VICTOR21-A/DSA2040A_ET_Exam_-Victor-_-388-?color=blue)
![GitHub last commit](https://img.shields.io/github/last-commit/VICTOR21-A/DSA2040A_ET_Exam_-Victor-_-388-)
![Python Version](https://img.shields.io/badge/python-3.8%2B-blue.svg)
![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)

---

##  Project Overview  
This repository presents a full **ETL (Extract → Transform → Load)** pipeline implemented in Python and Jupyter Notebooks as part of the End-Term Examination for the course DSA2040A.  
The project demonstrates how to:
- Extract raw data from source files  
- Inspect and validate data (identify issues such as nulls, duplicates, inconsistent types)  
- Transform and enrich the dataset using a minimum of five operations across at least three different categories (cleaning, standardization, enrichment, structural, filtering, categorization)  
- Persist the transformed data to structured output files  
- Provide full documentation and reproducibility of the pipeline  

---

##  Repository Structure  
```
DSA2040A_ET_Exam_-Victor-_-388-/
│
├── data.ipynb # Notebook for initial exploration and cleaning
├── data.py # Python module with reusable ETL functions
├── etl_extract.ipynb # Notebook for the Extract phase (20 marks)
├── etl_transform.ipynb # Notebook for the Transform phase (30 marks)
├── /data/ # Folder for raw and validated data versions
└── /transformed/ # Folder for final transformed outputs
```
---

## Dataset Description  
The dataset used in this project (e.g., `raw_data.csv`) is a raw, unprocessed file intended for ETL demonstration.  
It contains various data quality issues—including missing values, duplicates, inconsistent column names/types—making it suitable for practicing and showcasing data engineering operations.

Typical dataset characteristics include:
- Mixed data types (numeric, text, date)  
- Formatting inconsistencies (column names, cases, date formats)  
- Missing or null entries  
- Duplicate or incremental records  

This dataset is the input for both the extraction and transformation notebooks.

---

##  Extract Phase  — `etl_extract.ipynb`  
In this phase:  
1. The dataset(s) are loaded into Pandas DataFrames (using `data.py` helper functions).  
2. Exploratory inspection is carried out using `.head()`, `.info()`, `.describe()`.  
3. At least three data quality issues are identified and discussed (e.g., nulls, duplicates, inconsistent types).  
4. When applicable, datasets are merged/appended (e.g., base + incremental) and the reasoning is documented.  
5. Validated copies of cleaned data are saved to the `/data/` folder.  
6. All steps are annotated with markdown commentary in the notebook for clarity and reproducibility.

---

##  Transform Phase  — `etl_transform.ipynb`  
In this phase:  
- A minimum of five transformations are applied, drawn from at least three categories:  
  - **Cleaning** (e.g., drop duplicates, fill nulls)  
  - **Standardization** (e.g., rename columns, fix date formats)  
  - **Enrichment** (e.g., derive new columns like `total_cost`)  
  - **Structural** (e.g., change data types, split/merge columns)  
  - **Filtering** (e.g., remove irrelevant rows/columns)  
  - **Categorization** (e.g., binning continuous variables)  
- The resulting data is exported to two files:  
  - `transformed_full.csv`  
  - `transformed_incremental.csv`  
- Both output files are saved in the `/transformed/` folder.  
- The notebook is designed to be **re-runnable** from start to finish with no manual edits.

---

##  Helper Module — `data.py`  
This module encapsulates reusable functions for ETL tasks, such as:
- `load_data(path)`: load CSV/Excel data  
- `clean_data(df)`: perform data cleaning routines  
- `save_data(df, output_path)`: persist cleaned DataFrame to file  

Using `data.py` ensures that your code is modular, maintainable, and easy to reuse across notebooks.

---
Key Output Examples

After running the pipeline, you’ll find structured, clean output files such as:
```
/validated.csv
/validated_incremental.csv

/transformed.csv
/transformed_incremental.csv
```
##  Setup & Usage  
1. **Clone the repository**  
   ```bash
   git clone https://github.com/VICTOR21-A/DSA2040A_ET_Exam_-Victor-_-388-.git
   cd DSA2040A_ET_Exam_-Victor-_-388-
