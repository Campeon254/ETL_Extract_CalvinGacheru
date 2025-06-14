# ETL Pipeline: Data Extraction and Transformation
This project demonstrates how to implement an **ETL (Extract, Transform, Load)** pipeline using Python and a synthetic banking dataset.

**Name:** Calvin Gacheru  

---

## Project Overview

This project implements an end-to-end ETL pipeline simulating a data engineering workflow. It covers the process from data generation and extraction to cleaning, deduplication, aggregation, and enrichment. The goal is to replicate real-world data ingestion and transformation strategies using both full and incremental extraction approaches.

The pipeline covers two key stages:
1.  **Extraction**: Implements both **full** and **incremental** data extraction methods to pull data from a source.
2.  **Transformation**: Applies data cleaning, feature enrichment, and categorization to prepare the data for analysis.

All logic is implemented and documented within a single Jupyter Notebook.

---

## Tools Used

- **Python** (3.x)
- **Pandas** (data processing)
- **NumPy** (data generation)
- **datetime** (date manipulation)
- **random** (for random data generation)
- **Jupyter Notebook** (for documentation and interactivity)
- **Git/GitHub** (for version control and collaboration)

---

## Project Structure
ETL_Extract_CalvinGacheru/

├── etl_pipeline.ipynb # Main Jupyter Notebook

├── banking_data_large.csv # Simulated dataset (100+ records)

├── last_extraction.txt # Timestamp tracker for incremental loads

├── transformed_full.csv # Transformed dataset for full extraction

├── transformed_incremental.csv # Transformed dataset for incremental extraction

├── .gitignore # Ignoring unnecessary files

├── README.md # This file

---

## How It Works

The pipeline is executed in two main stages within the `etl_pipeline.ipynb` notebook.

### **Stage 1: Extraction**

This stage focuses on getting the raw data.

#### **Data Generation**

100+ records of user banking activity between May 1, 2025 and May 31, 2025.

- Users: `user_1` to `user_49`
- Events: `deposit`, `withdraw`, `loan_application`, `atm_withdrawal`, `login`
- Dates: From **May 1, 2025** to **May 31, 2025**

#### **Extraction Methods**
- **Full Extraction**: Pulls the entire dataset from the source.
- **Incremental Extraction**: Pulls only new records since the last extraction, using a timestamp tracker stored in `last_extraction.txt`.

### **Stage 2: Transformation**
This stage processes the raw data to make it suitable for analysis.

#### **1. Data Cleaning**
* **Missing Values Check**: The dataset is scanned to ensure there are no null values.
* **Duplicate Removal**: Duplicate rows (~5% injected for simulation) are identified and removed to ensure data accuracy.

#### **2. Data Enrichment**
* **Extract `hour` from Timestamp**: A new `hour` column is created from the `timestamp` to enable time-based analysis, such as identifying peak activity hours.

#### **3. Categorization**:
The `event` column is categorized into `transactional` (deposit, withdraw, atm_withdrawal) and `non-transactional` (loan_application, login) for better analysis.

#### **4. Aggregation**:
Grouped by user_id and event, computing:
* Total amount
* Number of events (event_count)
* Unique loan statuses (if applicable)

---

## Output Files
- **`banking_data_large.csv`**: The simulated dataset with 100+ records.
- **`Transformed_full_ext.csv`**: The transformed dataset after full extraction.
- **`Transformed_incremental_ext.csv`**: The transformed dataset after incremental extraction.
- **`last_extraction.txt`**: A text file that stores the timestamp of the last extraction for incremental loads.


---

## How to Reproduce
1. **Clone the Repository**:
```bash
   git clone https://github.com/Campeon254/ETL_Extract_CalvinGacheru.git

   cd ETL_Extract_CalvinGacheru
```
2. **Install Dependencies**:

   Ensure you have Python 3.x installed, then install the required libraries:
```bash
   pip install pandas numpy
```
3. **Run the Notebook**:
   Open `etl_pipeline.ipynb` in Jupyter Notebook or JupyterLab:
```bash
   jupyter notebook etl_pipeline.ipynb
```
The notebook will:
* Simulate and save the dataset
* Perform full extraction
* Simulate a previous timestamp
* Perform incremental extraction
* Update the timestamp tracker

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.