# Cleaning-Data-with-Python---Marketing-Campaign-DataSet
## 📌 Project Overview
In the real world, data is rarely "clean." Marketing data, in particular, often arrives from various platforms (TikTok, Google Ads, Facebook) with inconsistent formats, duplicate entries, and statistical noise.

This project demonstrates a comprehensive Data Cleaning Pipeline using Python. I transformed a raw, "messy" marketing dataset into a high-quality, analysis-ready asset, ensuring that business decisions are based on accurate and standardized metrics.

## 🛠️ The Challenge: Why did this data need cleaning?
The raw dataset (marketing_campaign_data_messy.csv) contained several critical issues that would mislead any analysis:

Structural Errors: Duplicate columns (e.g., two Clicks columns) and trailing spaces in headers.

Data Type Inconsistency: The Spend column was stored as a string with currency symbols ($), and dates had mixed formats.

Categorical Noise: The Channel and Active columns used non-standard labels (e.g., 'Email', 'EM', 'E-mail' for the same category; 'Y', 'Yes', 'True', '1' for active status).

Missing Values: Significant gaps in Campaign_Tag and other key metrics.

Extreme Outliers: Statistical anomalies in the Spend column (values up to $500,000) that skewed the ROI calculations.

## ⚙️ Data Cleaning Workflow
I implemented a structured cleaning process in the Clean_Marketing.ipynb notebook:

### 1. Robust Header Normalization
Stripped leading/trailing whitespaces from column names.

Converted all headers to lowercase and replaced spaces with underscores for better coding accessibility.

Resolved duplicate column issues to prevent data redundancy.

### 2. Type Conversion & Regex Parsing
Utilized Regular Expressions (Regex) to strip $ and , from the Spend column, converting it to a float.

Standardized start_date and end_date into a unified datetime64 format.

### 3. Categorical Standardization (Mapping)
Applied mapping dictionaries to unify categories:

Channel: Standardized variations into ['TikTok', 'Facebook', 'Email', 'Google Ads'].

Status: Converted 'Y', '1', 'Yes' into a consistent Boolean True/False format.

### 4. Advanced Outlier Detection
Methodology: Used the Interquartile Range (IQR) method with a 3.0x multiplier to identify extreme outliers.

Action: Identified and handled artificial spend spikes (e.g., $500k entries) which were likely data entry errors, ensuring the mean spend reflects reality.

## 📊 Tech Stack
Language: Python 3.x

Key Library: Pandas (Data manipulation), NumPy (Mathematical operations).

Environment: Jupyter Notebook.

## 📈 Impact & Results
Data Integrity: Improved from a "messy" state to 100% consistency across all 1,500+ records.

Ready for BI: The cleaned data is now perfectly formatted for visualization tools like Tableau, Power BI, or Looker Studio.

Accurate Metrics: By removing outliers and standardizing spend, the calculated CPC (Cost Per Click) and CTR (Click-Through Rate) are now accurate for performance marketing audits.
