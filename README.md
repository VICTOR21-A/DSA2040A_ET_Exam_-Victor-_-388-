#  DSA2040A – ET Exam (Victor – 388)
*A complete ETL (Extract, Transform, Load) pipeline implemented in Python and SQLite.*

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python)
![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-yellow?logo=pandas)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## 📘 Table of Contents
1. [Project Overview](#project-overview)
2. [Repository Structure](#repository-structure)
3. [Dataset Description](#dataset-description)
4. [Extract Phase](#extract-phase)
5. [Transform Phase](#transform-phase)
6. [Helper Module: `data.py`](#helper-module-datapy)
7. [Setup & Usage](#setup--usage)
8. [Requirements](#requirements)
9. [How to Run](#how-to-run)
10. [Expected Outputs](#expected-outputs)
11. [Project Credits & Acknowledgements](#project-credits--acknowledgements)
12. [License](#license)
13. [Contact](#contact)

---

## 🚀 Project Overview
This project demonstrates a **complete ETL (Extract, Transform, Load)** pipeline for the course module **DSA2040A – End-Term Exam**.  
It showcases a systematic approach to data processing — from raw data collection to validated and transformed datasets ready for analytics.

**Key Highlights:**
- 📥 Extraction and validation of raw datasets  
- 🔄 Transformation and enrichment of cleaned data  
- 💾 Export of final structured datasets  
- 🧩 Modular and reusable Python code design  

**Technologies Used:**
- 🐍 Python (Pandas, NumPy, SQLite3)
- 📓 Jupyter Notebook
- ⚙️ Modular scripting with `data.py`

---

## 📁 Repository Structure
```plaintext
DSA2040A_ET_Exam_-Victor-_-388-/
│
├── data/                          # Contains all datasets
│   ├── raw/                       # Original unprocessed data
│   └── validated/                 # Cleaned and validated data
│
├── transformed/                   # Folder for transformed datasets
│   ├── transformed_full.csv
│   └── transformed_incremental.csv
│
├── etl_extract.ipynb              # Data extraction and validation notebook
├── etl_transform.ipynb            # Data transformation notebook
├── data.py                        # Helper module with ETL functions
└── README.md                      # Project documentation
````

---

## 📊 Dataset Description

The dataset simulates **real-world data challenges** to demonstrate data cleaning and transformation skills.

### ⚙️ Common Issues Addressed

* Missing or null values
* Duplicate and incremental records
* Inconsistent naming conventions
* Mixed data types (numeric/text/date)
* Irregular date and text formatting


---

## 🧩 Extract Phase

**Notebook:** `etl_extract.ipynb`

This phase focuses on data **ingestion, inspection, and validation**.

### 🧠 Key Steps:

1. Load raw datasets using `data.py` helper functions.
2. Inspect dataset structure and content using `.info()`, `.head()`, `.describe()`.
3. Identify and document data quality issues.
4. Clean and validate the dataset (e.g., remove duplicates, fill nulls, rename columns).
5. Save validated data into `data/validated/`.

### 💻 Example Code

```python
from data import load_data, clean_data, save_data

df_raw = load_data("raw_data.csv")
df_clean = clean_data(df_raw)
save_data(df_clean, "validated_data.csv")
```

🗂️ *Output:* A validated, cleaned dataset ready for transformation.

---

## 🔁 Transform Phase

**Notebook:** `etl_transform.ipynb`

This phase applies multiple **data transformations** across various categories.

### 🧮 Transformation Categories

| Category           | Operation Example                              | Goal             |
| :----------------- | :--------------------------------------------- | :--------------- |
| Cleaning           | Remove nulls, trim whitespace                  | Ensure accuracy  |
| Standardization    | Rename columns, fix data types                 | Consistency      |
| Enrichment         | Derive                                         | Add value        |
| Filtering          | Remove irrelevant rows                         | Focused data     |
| Structural Changes | Merge/split columns, change types              | Organized schema |

### 📤 Output Files

* `transformed.csv` – Final comprehensive dataset
* `transformed_incremental.csv` – Incremental updates dataset

📝 *Each transformation is clearly documented in markdown cells with visual outputs.*

---

## ⚙️ Helper Module: `data.py`

The `data.py` file contains modular, reusable functions for data handling.

### 🔧 Example Functions

```python
import pandas as pd

def load_data(path):
    """Load dataset into a pandas DataFrame."""
    return pd.read_csv(path)

def clean_data(df):
    """Clean and standardize the dataset."""
    df = df.drop_duplicates()
    df = df.fillna(0)
    df.columns = [col.strip().lower().replace(" ", "_") for col in df.columns]
    return df

def save_data(df, output_path):
    """Save the cleaned/transformed DataFrame to a CSV file."""
    df.to_csv(output_path, index=False)
```

🧱 *This modular approach ensures cleaner, more maintainable code.*

---

## ⚙️ Setup & Usage

### 💡 Requirements

* Python 3.8+
* Libraries:

  ```bash
  pip install pandas numpy jupyter
  ```

---

## ▶️ How to Run

1. **Clone the repository**

   ```bash
   git clone https://github.com/VICTOR21-A/DSA2040A_ET_Exam_-Victor-_-388-.git
   cd DSA2040A_ET_Exam_-Victor-_-388-
   ```

2. **Launch Jupyter Notebook**

   ```bash
   jupyter notebook
   ```

3. **Run Extraction Notebook**

   * Open `etl_extract.ipynb`
   * Run all cells
   * Validate the output in `data/validated/`

4. **Run Transformation Notebook**

   * Open `etl_transform.ipynb`
   * Run all cells
   * View results in `transformed/`

---

## 📈 Expected Outputs

| Folder            | File                          | Description                       |
| :---------------- | :---------------------------- | :-------------------------------- |
| `validated/`      | `validated_data.csv`          | Cleaned and validated dataset     |
| `transformed/`    | `transformed.csv`             | Fully transformed dataset         |
| `transformed/`    | `transformed_incremental.csv` | Incrementally transformed dataset |

✅ *Final datasets are ready for analytics, reporting, or database integration.*

---

## 🙌 Project Credits & Acknowledgements

* 👨‍💻 **Developer:** Victor (Student ID: 388)
* 🏫 **Course:** DSA2040A – End-Term Exam
* 📚 **Institution:** USIU
* 🧑‍🏫 **Instructor:** A. ODERA

**Acknowledgements**

* Open-source Python community
* Libraries: `pandas`, `numpy`, `sqlite3`
* Tools: Jupyter Notebook, VS Code

---

## 📜 License

This project is licensed under the **MIT License**.
You are free to use, modify, and distribute this code with attribution.
See the [LICENSE](LICENSE) file for full details.

---

## 📬 Contact

📧 **Victor**
🔗 [GitHub Profile](https://github.com/VICTOR21-A)
💬 *For feedback, collaborations, or inquiries — feel free to reach out!*

---



