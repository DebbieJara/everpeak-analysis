# 🛍️ Retail Transactions — End-to-End Data Quality & Exploratory Analysis

End-to-end data quality audit and exploratory analysis applied to a retail 
transactions dataset containing 2,000 customer orders across multiple product 
categories, payment methods, and regions.

## 📂 Repository Contents

- `retail_data_analysis.ipynb` — Main notebook: data cleaning, EDA, 
  distributions, outlier detection, and feature engineering
- `everpeak_retail.csv` — Dataset used in the analysis

## ▶️ Open in Google Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/DebbieJara/everpeak-analysis/blob/main/retail_data_analysis.ipynb)

## 📋 What This Project Covers

- **Data Quality Audit** — structure inspection, missing values, invalid dates
- **Missing Value Analysis** — pattern classification and imputation strategy selection
- **Reusable Cleaning Pipeline** — modular functions applicable to similar datasets
- **Statistical Profiling** — numeric and categorical summaries by product category
- **Distribution Visualizations** — histograms and boxplots with Matplotlib and Seaborn
- **Outlier Detection** — IQR and Z-score methods compared
- **Feature Engineering** — customer segmentation using `np.where()` and `apply()`

## 🛠️ Stack

Python · pandas · NumPy · Matplotlib · Seaborn
