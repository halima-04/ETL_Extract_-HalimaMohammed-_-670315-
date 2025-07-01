# ETL_Extract_-HalimaMohammed-_-670315-
# ETL Extract Lab

Name: Halima Mohammed
Student ID: 670315

## 📄 Description
This project demonstrates Full and Incremental Extraction using ETL techniques on a synthetic sales dataset.

## STRUCTURE OF THE ETL_Extract_-HalimaMohammed-_-670315-
- .gitignore
- last_extraction.txt 
- etl_extract.ipynb 
- README.md
  
 custom_data.csv 

## 🔧 Tools Used
- Python
- Pandas
- Jupyter Notebook

##  How to Reproduce
1. Clone the repo
2. Run `etl_extract.ipynb` in Jupyter
3. Data is loaded from `custom_data.csv`
4. Incremental extraction reads from and writes to `last_extraction.txt`

## 📊 Data Source
Synthetic sales data generated using Python


## 🔧 Lab 4 – Transformation

**Transformations applied to both full and incremental data:**

1. **Cleaning:**  
   - Removed duplicate rows  
   - Handled any missing values

2. **Enrichment:**  
   - Added a new column `Category` based on `Amount`  
     (e.g., Low, Medium, High)

3. **Structural:**  
   - Converted `Timestamp` to datetime format  
   - Standardized date column

**Output Files:**
- `transformed_full.csv`
- `transformed_incremental.csv`

---

## 📁 Files in This Repository

| File                          | Description                        |
|-------------------------------|------------------------------------|
| `etl_extract.ipynb`           | Main notebook for ETL steps        |
| `custom_data.csv`             | Raw extracted data                 |
| `transformed_full.csv`        | Transformed full dataset           |
| `transformed_incremental.csv` | Transformed incremental dataset    |
| `.gitignore`                  | Excludes temporary files           |
| `README.md`                   | Project description (this file)    |

---

## ✅ How to Run

1. Clone the repo  
2. Open `etl_extract.ipynb` in Jupyter Notebook  
3. Run all cells to generate transformed datasets



## 🧪 Lab 5 – Load Phase

This lab focuses on the **Load** step in the ETL (Extract, Transform, Load) pipeline. After transforming the data in previous labs, the cleaned datasets are now loaded into structured storage formats for querying and analysis.

---

## ✅ Loading Method Used

- The transformed CSV files were loaded into **SQLite databases** using Python’s `sqlite3` library.

---

## ⚙️ Tools & Libraries

| Tool         | Purpose                        |
|--------------|---------------------------------|
| Python 3.12  | Programming language            |
| Pandas       | Data loading & manipulation     |
| SQLite3      | Lightweight SQL database engine |
| Jupyter Lab  | Notebook interface              |

---

## 🧩 Sample Code Snippet (SQLite Load)

```python
import pandas as pd
import sqlite3

# Load full dataset into SQLite
df_full = pd.read_csv("transformed_full.csv")
conn = sqlite3.connect("loaded_data/full_data.db")
df_full.to_sql("full_data", conn, if_exists="replace", index=False)
conn.close()


