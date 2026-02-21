# EHR Data Cleaning Pipeline: Clinical Standardization

## 📌 Project Overview
Clinical data exported from Electronic Health Records (EHR) is notoriously inconsistent. This project demonstrates a Python-based **Data Cleaning Pipeline** that transforms a "dirty" clinical dataset (containing unit mismatches, inconsistent diagnosis strings, and impossible outliers) into a standardized, research-ready format.

## 🛠️ The "Dirty Data" Problem
The raw dataset simulated common real-world clinical data issues:
* **Unit Mismatches:** Weight recorded in both `kg` and `lbs`.
* **Scale Inconsistency:** Height recorded in both `meters` and `centimeters`.
* **Categorical Noise:** Five different variations of "Type 2 Diabetes" (e.g., T2DM, DMII).
* **Physiological Outliers:** Impossible Blood Pressure readings (e.g., 900 mmHg systolic).

## 📊 Data Transformation Dashboard
<img width="4446" height="1745" alt="ehr_cleaning_summary" src="https://github.com/user-attachments/assets/cde821a5-e8a6-4e43-afae-b97c891506b7" />


*Figure 1: Post-cleaning validation. Left: Standardized diagnosis categories. Right: Validated BMI distribution.*

## 🚀 Key Data Engineering Steps
* **Unit Standardization:** Custom Python functions to detect strings (`lbs` vs `kg`) and apply mathematical conversions ($lbs \times 0.453$).
* **Mapping Dictionaries:** Used dictionary-based grouping to consolidate inconsistent medical terminology into a single "Gold Standard" category.
* **Outlier Filtering:** Implemented clinical logic to identify and nullify physiologically impossible values (e.g., Systolic BP > 300).
* **Derived Metrics:** Calculated **Body Mass Index (BMI)** using cleaned Weight and Height fields to prove data integrity.

## 🛠️ Tech Stack
* **Language:** Python
* **Libraries:** Pandas, NumPy
* **Visualization:** Seaborn, Matplotlib
* **Environment:** Google Colab

## 📂 How to Run
1. Open the notebook in **Google Colab**.
2. Run the **"Dirty" Data Generator** to create the `messy_ehr_data.csv`.
3. Execute the **Cleaning Pipeline** cells to witness the transformation.
4. Review the **Final Cleaned Dataframe** and the generated **Validation Dashboard**.
