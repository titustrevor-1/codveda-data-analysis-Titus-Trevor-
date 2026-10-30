# Task 1: Data Cleaning and Preprocessing

## Objective
Clean the churn dataset so it is ready for analysis.

## Dataset
- File: churn-bigml-20.csv
- Rows: 667
- Columns: [number]

## Problems Found
- Missing values: none
- Duplicate rows: none
- Outliers: some, kept because they are real customers

## What I Did
1. Checked the size and data types
2. Checked for missing values and duplicates
3. Checked the column names
4. Checked for outliers with a box plot
5. Turned the state column into number columns
6. Scaled the number columns
7. Saved the clean data

## Result
Final shape: [rows, columns]
Clean file: cleaned_churn_data.csv

## Tools
Python, pandas, matplotlib, scikit-learn