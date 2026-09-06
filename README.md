# Zen EliteStride Maison - Python Sales Analysis (pandas / Jupyter Notebook)

Fourth stage of a five-part analytics pipeline built on the same shoe sales
dataset: **Excel → Power BI → SQL → Python → Machine Learning**. This stage
recreates the same KPIs and business questions in Python, in an annotated
Jupyter Notebook.

## Overview

Zen EliteStride Maison is a fictional footwear retailer. The dataset covers
500 transactions across 8 products, 4 categories, 6 brands, and 14
countries. This notebook answers management's core business questions
using pandas, with every step explained in markdown cells alongside the
code.

## Business questions answered

1. How is the business performing overall?
2. How have revenue and profit changed over time?
3. Which products are driving sales?
4. Which products are driving profitability?
5. Which categories and brands perform best?
6. Which countries contribute the most to the business?
7. What purchasing patterns can we identify from payment method and product preferences?
8. What actions should management take based on the findings?

## Key findings

- **Total revenue: 355,048 | Total profit: 162,335 | Margin: 45.72%**, consistent (42-48%) every month.
- **Formal category, especially Clarks and Zara**, is the strongest revenue and profit driver.
- **Derby** has the highest profit margin of any product (56.25%) but the lowest volume - a likely visibility/marketing gap rather than weak demand.
- **USA, UK, and Ghana** are the top three markets by revenue; Albania, Canada, and Australia trail furthest behind.
- These figures match the validated Power BI and SQL stages of this pipeline exactly, confirming the analysis is consistent across tools.

## Data cleaning

The raw data has inconsistent casing and stray whitespace in text columns
(e.g. `'monk straps '`, `'MONK STRAPS'`, `'Monk Straps'` all refer to the
same product). The notebook standardizes these with `.str.strip()` and
`.str.title()` before merging sales with price data, and includes a data
quality check confirming zero unmatched products after cleaning - the same
bug found and fixed in the Power BI and SQL stages.

## Tech stack

- Python 3.9+
- pandas
- matplotlib / seaborn
- openpyxl
- Jupyter Notebook

## Files in this repo

| File | Description |
|---|---|
| `shoe_sales_analysis.ipynb` | Full annotated notebook - data loading, cleaning, all 7 business questions, charts, and management recommendations |
| `shoe_sales_dashboard_python.png` | Exported 4-panel summary chart |
| `Zen_EliteStride_Maison_Python.xlsx` | Source dataset |

## How to run this

1. Install Python, then `pip install jupyter pandas matplotlib seaborn openpyxl`.
2. Put the notebook and the Excel file in the same folder.
3. Run `jupyter notebook` and open `shoe_sales_analysis.ipynb`.
4. Run all cells top to bottom.

## Part of a larger pipeline

This is stage 4 of 5. The same dataset and business questions are also
answered in:

- **Excel** - pivot-table dashboard
- **Power BI** - DAX measures and interactive report
- **SQL (PostgreSQL / pgAdmin)** - schema, cleaning views, window functions, indexing, a stored procedure, and role-based access control
- **Machine Learning** - regression and classification models testing whether order size and payment method are predictable from order attributes

## Author

Tusnelde Endjala
