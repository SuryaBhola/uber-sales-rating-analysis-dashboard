# E-Commerce Customer & Sales Analysis

An end-to-end data analysis project on e-commerce order data — from raw, messy source files to a cleaned data model and an interactive Power BI dashboard.

## What this project covers

I started with four raw source tables exported from the business (customers, orders, order items, and products), cleaned them up in Python/pandas, built a small star-schema-style data model, and put together a one-page Power BI dashboard on top of it to track sales, returns, and customer behavior.

## The data

**Raw files** (as exported, with the usual real-world mess — inconsistent date formats, mixed-case text, missing values):
- `customers.csv` — 1,225 customers
- `orders.csv` — 4,515 orders
- `order_items.csv` — 11,350 line items
- `products.csv` — 40 products

**Cleaned files** (after processing):
- `customers_clean.csv` — 1,200 rows (duplicates/invalid records removed), city names standardized to title case, missing phone numbers filled with `Unknown`, signup dates normalized to `YYYY-MM-DD`
- `orders_clean.csv` — 4,500 rows, order dates normalized, missing payment modes filled with `Unknown`, rating stored as a consistent numeric type
- `order_items_clean.csv` — 11,350 rows, with a `transaction_type` column added to flag sales vs. returns
- `products_clean.csv` — 40 rows, category casing standardized (e.g. `electronics` → `Electronics`)

**Supporting model tables:**
- `dim_date.csv` — a full calendar table (365 days) with year, quarter, month, and day breakdowns for time intelligence in Power BI
- `fact_sales_dashboard.csv` — the final flattened fact table (11,350 rows × 31 columns) joining orders, order items, products, and customers, with net sales, gross sales, return value, and return quantity already calculated — this is what the dashboard is actually built on

## Tools

- **Python (pandas, numpy)** — data cleaning and transformation
- **Power BI Desktop** — data modeling, DAX measures, dashboard build

## The dashboard

One page, built to give a quick but complete read on the business:

- KPI cards up top: Net Sales, Total Orders, Gross Sales, Return Value, Return Rate
- Net Sales trend by month
- Net Sales by product category
- Net Sales by region
- Top products by net sales
- Orders split by payment mode (donut chart)
- Return Value by category — to see which categories are hurting margins
- Return Value trend over time

## Key measures (DAX)

- Net Sales, Gross Sales, Return Value, Return Rate
- Total Orders
- Sum of net sales (product-level)

## Repo contents

```
├── customers.csv
├── customers_clean.csv
├── orders.csv
├── orders_clean.csv
├── order_items.csv
├── order_items_clean.csv
├── products.csv
├── products_clean.csv
├── dim_date.csv
├── fact_sales_dashboard.csv
├── E-commerce_Customer_&_Sales_Python.py     # cleaning script
├── E-commerce_Cuastomer_&_Sales_Analysis.pbix # Power BI report
└── README.md
```

## Running it

1. If you want to see the cleaning steps, check the Python script — it loads the four raw source files and processes them into the `_clean` versions.
2. To explore the dashboard, just open the `.pbix` file in Power BI Desktop.

## About me

Surya Bhola — data analyst working mainly in SQL, Python, Excel, and Power BI.
[LinkedIn](https://linkedin.com/in/suryabhola-da)
