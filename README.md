# Retail Transactions: End-to-End Data Quality & Exploratory Analysis

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/DebbieJara/everpeak-retail-data-quality-analysis/blob/main/retail_data_analysis.ipynb)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=flat&logo=pandas&logoColor=white)

**Business question:** Before any purchase behavior analysis can be trusted, the underlying data needs to be reliable. This project asks: how much can we trust this retail transactions dataset, and what does it take to make it analysis-ready?

## Context

The dataset contains 2,000 customer orders across multiple product categories, payment methods, and regions, including order values, product categories, payment methods, and demographic information.

## Process

I applied a full data quality and exploratory analysis workflow: auditing structure and missing values, investigating the pattern behind missingness rather than applying a single imputation rule, building a reusable and documented cleaning pipeline, profiling statistics by product category, visualizing distributions, comparing two outlier detection methods, and engineering customer segments for downstream targeting.

## Key findings

| Topic | Finding |
|---|---|
| Missing values | `city` and `state` had the highest null rates; `order_date` contained future-dated records (year 2026) requiring filtering |
| Missingness pattern | The null rate for `city` varied across payment method groups, indicating the data is Missing At Random (MAR), not Missing Completely At Random. This was handled with conditional logic rather than a single global imputation rule |
| Distribution shape | `order_value` and `price` are right-skewed; median was used as the preferred central tendency measure to avoid distortion from extreme values |
| Outlier detection | The IQR method flagged more records than the Z-score method on these skewed columns, consistent with expected behavior. Extreme values were isolated for review rather than dropped outright |
| Customer segments | Four customer segments were created from age and purchase volume (e.g. Sr. High Volume, Jr. Low Volume), plus a separate payment-behavior segmentation combining card usage and volume, adding a behavioral dimension for targeted strategies |

## Technical details

### Dataset

| Column | Type | Description |
|---|---|---|
| order_id | string | Unique order identifier |
| order_date | date | Purchase date |
| customer_id | int | Unique customer identifier |
| product_category | string | e.g. Fashion, Grocery, Sports |
| price | float | Unit price |
| quantity | float | Units purchased |
| order_value | float | Total transaction amount |
| payment_method | string | Payment method used |
| city | string | Customer city |
| state | string | Customer state |
| customer_age | float | Customer age |

### Analytical workflow

| Step | Description |
|---|---|
| 1. Data quality audit | Structure inspection, missing value counts, cardinality checks, date range validation |
| 2. Missing value analysis | Tested whether missingness patterns depended on other variables (MAR) before choosing an imputation strategy |
| 3. Reusable cleaning pipeline | Modular, single-purpose functions (sentinel replacement, numeric imputation, text cleaning) orchestrated by one pipeline function |
| 4. Statistical profiling | Numeric and categorical summaries by product category; mean vs. median comparison to detect skew |
| 5. Distribution visualizations | Histograms and boxplots with Matplotlib and Seaborn |
| 6. Outlier detection | IQR and Z-score methods applied and compared |
| 7. Feature engineering | Customer segmentation using `np.where()` and `apply()` with custom classification functions |

### Key skills demonstrated

- Missing data pattern classification (MAR vs. MCAR) before choosing an imputation strategy
- Modular, reusable data cleaning pipeline design
- Statistical profiling and skew detection
- Outlier detection using multiple methods (IQR, Z-score)
- Feature engineering for customer segmentation

## Tools

Python · pandas · NumPy · Matplotlib · Seaborn

## Repository structure

```text
everpeak-retail-data-quality-analysis/
├── README.md
├── retail_data_analysis.ipynb
└── everpeak_retail.csv
```

---

By Deborah Jara | Business Intelligence · Data Analytics | Mexico
[LinkedIn](https://www.linkedin.com/in/deborahjara) · [GitHub](https://github.com/DebbieJara)
