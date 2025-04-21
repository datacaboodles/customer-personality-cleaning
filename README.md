**# customer-personality-cleaning

Data cleaning task - missing values, formatting, outlier removal

# 🧹 Customer Personality Analysis – Data Cleaning Project

This repository contains my work on cleaning and preprocessing the **Customer Personality Analysis** dataset using Python and Pandas. This task was part of a Data Analyst internship assignment, where I was required to handle real-world data issues such as missing values, duplicates, formatting problems, and outliers — and make the dataset ready for analysis or modeling.

---

## 🧠 Objective

The main goal was to clean a raw marketing dataset that includes customer demographics, purchase behavior, and campaign response history. I followed a structured approach to:

- Understand the structure and issues in the data
- Apply appropriate cleaning techniques
- Document everything I did for clarity and reproducibility

---

## 🧪 Dataset Overview

The dataset contains 2,240 records and 29 features including:

- **Customer demographics**: Age, Education, Marital Status, Income, Children
- **Spending habits**: Amounts spent on wine, meat, fruits, etc.
- **Marketing interactions**: Acceptance of different campaigns, complaints, and response
- **Date fields**: Customer registration date

---

## 🔍 My Step-by-Step Approach

## Part 1: Initial Data Exploration
- Loaded the CSV file using `pandas.read_csv()` with a tab (`\t`) separator
- Inspected the shape, column names, and sample rows
- Used `.info()` and `.describe()` to assess data types, nulls, and distributions
- Identified:
  - 24 missing values in the `Income` column
  - Some inconsistent text values in `Marital_Status` and `Education`
  - A possible outlier (`Income = 666666`)
  - All column names were in mixed case with underscores

## Part 2: Data Cleaning

### ✅ 1. Renamed Columns
Converted all column names to lowercase and removed spacing issues for consistency:
df.columns.str.lower().str.replace(" ", "_")

### ✅ 2. Handled Missing Values
Filled missing values in the income column using the median income, which is robust to outliers.

### ✅ 3. Converted Date Format
Converted the dt_customer column from object to proper datetime format using:
pd.to_datetime(..., dayfirst=True)

### ✅ 4. Standardized Categorical Variables
Grouped inconsistent categories:

"2n Cycle" in education → grouped under "Master"

"YOLO", "Absurd", "Alone" in marital_status → grouped under "Single"

### ✅ 5. Removed Outliers
Dropped the one row with an unrealistic income of 666666.

## 📊 Final Cleaned Dataset
✅ 0 missing values
✅ Consistent and meaningful categories
✅ Clean and analysis-ready column names
✅ Proper date format
✅ Outliers removed

Cleaned file saved as: marketing_campaign_cleaned.csv

## 🛠️ Tools Used
Python 3
Jupyter Notebook
Pandas

## 📈 What I Learned
1. Hands-on experience with real-world data imperfections
2. Practical use of pandas for identifying and resolving data quality issues
3. How to structure a cleaning workflow from raw data to cleaned output
4. Gained confidence in handling messy data independently
**
