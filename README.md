# ETL_Extract_CalvinGacheru
This project demonstrates how to use full extraction and Incremental Extraction.

**Name:** Calvin Gacheru  

---

## Project Overview

This project demonstrates **ETL Extraction Techniques** using a synthetic dataset generated for the **banking industry**. The goal is to simulate realistic data and practice two key ETL methods:

- **Full Extraction**: Pulls all data regardless of changes.
- **Incremental Extraction**: Pulls only new or updated records based on a tracked timestamp.

The ETL logic is implemented inside a well-documented **Jupyter Notebook**. This project mimics real-world data workflows used in banking, fintech, and analytics.

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

├── etl_extract.ipynb # Main Jupyter Notebook

├── banking_data_large.csv # Simulated dataset (100+ records)

├── last_extraction.txt # Timestamp tracker for incremental loads

├── .gitignore # Ignoring unnecessary files

├── Folder containing screenshots

├── README.md # This file

---

## How It Works

### Data Generation

A synthetic dataset mimicking banking user activity was created with:

- Users: `user_1` to `user_49`
- Events: `deposit`, `withdraw`, `loan_application`, `atm_withdrawal`, `login`
- Dates: From **May 1, 2025** to **May 31, 2025**

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
   Open `etl_extract.ipynb` in Jupyter Notebook or JupyterLab:
```bash
   jupyter notebook etl_extract.ipynb
```
The notebook will:
* Simulate and save the dataset
* Perform full extraction
* Simulate a previous timestamp
* Perform incremental extraction
* Update the timestamp tracker

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.