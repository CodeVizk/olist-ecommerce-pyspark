# Olist E-Commerce Data Pipeline — PySpark + Databricks

## Overview

This is an end-to-end Data Engineering project built using PySpark and Databricks.
The project uses the Brazilian Olist E-Commerce dataset and processes raw CSV files through a Medallion Architecture pipeline:

* Bronze Layer → Raw ingestion
* Silver Layer → Cleaning and transformation
* Gold Layer → Business analytics and reporting

The goal of this project was to practice real-world data engineering concepts like ETL pipelines, distributed data processing, joins, window functions, Delta tables, and business KPI generation using Apache Spark.



---

## Dataset

Dataset Used:
**Brazilian E-Commerce Public Dataset by Olist**

Source:
[https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

### Tables Used

The project uses 9 CSV datasets:

1. customers
2. orders
3. order_items
4. products
5. sellers
6. payments
7. reviews
8. geolocation
9. category_translation

---

# Project Architecture

```text
                Raw CSV Files
                       |
                       v
              -----------------
              | Bronze Layer |
              -----------------
             Raw ingestion + validation
                       |
                       v
              -----------------
              | Silver Layer |
              -----------------
            Cleaning + transformations
                       |
                       v
              -----------------
              |  Gold Layer  |
              -----------------
              Business analytics
```

---

# Tech Stack

| Technology   | Usage                          |
| ------------ | ------------------------------ |
| PySpark      | Distributed data processing    |
| Apache Spark | Processing engine              |
| Databricks   | Notebook execution environment |
| Spark SQL    | SQL analytics                  |
| Delta Lake   | Table storage                  |
| Python       | Programming language           |

---

# Project Structure

```text
olist-ecommerce-pyspark/
│
├── 01_bronze_ingestion.ipynb
├── 02_silver_cleaning.ipynb
├── 03_gold_analytics.ipynb
├── README.md
└── dataset/
```

---

# Pipeline Flow

## 1. Bronze Layer — Raw Data Ingestion

Notebook:
`01_bronze_ingestion.ipynb`

### Tasks Performed

* Loaded all CSV files into Spark DataFrames
* Used schema inference
* Performed basic data quality checks
* Checked:

  * null values
  * duplicate values
  * row counts
* Performed exploratory data analysis
* Saved raw tables into Bronze Delta tables

### Bronze Layer Analysis

Some basic EDA was performed:

* Customer distribution by state
* Order status distribution
* Payment type analysis
* Top selling products
* Delivery time analysis

### Bronze Tables Created

* bronze_customers
* bronze_orders
* bronze_order_item
* bronze_products
* bronze_sellers
* bronze_payments
* bronze_reviews
* bronze_geolocation
* bronze_translation

---

## 2. Silver Layer — Cleaning & Transformation

Notebook:
`02_silver_cleaning.ipynb`

### Tasks Performed

### Missing Value Handling

* Removed rows with missing critical IDs
* Filled missing delivery dates
* Used PySpark Imputer for numerical missing values

### Data Standardization

* Checked schemas
* Converted data types
* Standardized timestamp columns

### Deduplication

Duplicate records were identified and removed.

### Joins

Multiple datasets were joined together to create unified analytical tables.

Broadcast joins were used for optimization.

### Final Silver Tables

* silver_customers
* silver_orders
* silver_order_item
* silver_products
* silver_sellers
* silver_payments
* silver_reviews
* silver_geolocation
* silver_translation
* silver_full_order

---

## 3. Gold Layer — Business Analytics

Notebook:
`03_gold_analytics.ipynb`

The Gold Layer contains analytics-ready tables for business insights.

### Analytics Performed

## Order Analytics

* Total order value
* Order revenue calculation
* Monthly revenue trends
* Order count trends

## Customer Analytics

* Top customers by spending
* Customer Average Order Value (AOV)
* Customer segmentation
* Customer retention analysis

### Customer Segments

Customers were segmented into:

* High value
* Medium value
* Low value

## Seller Analytics

* Seller revenue ranking
* Seller performance metrics
* Average review score per seller
* Total orders per seller

## Product Analytics

* Top selling products
* Product popularity metrics
* Product revenue analysis
* Price volatility analysis
* Multi-seller product analysis

## Time-Based Analytics

* Monthly sales trends
* Hourly ordering patterns
* Weekday vs weekend analysis

## Window Functions Used

* rank()
* dense_rank()
* lag()
* lead()

---

# Gold Tables Generated

Some analytics tables created:

* order_total_value
* total_revenue
* total_orders_per_customer_df
* review_score
* top_products_df
* top_customer_df
* seller_rank_revenue
* customer_spend_df
* seller_performance_df
* product_metrics_df
* month_order_detail_df
* customer_retention_df

---

# PySpark Concepts Used

## Data Processing

* Spark DataFrames
* Transformations and actions
* Lazy evaluation
* Distributed processing

## Data Cleaning

* fillna()
* dropna()
* Imputer
* Deduplication

## Aggregations

* groupBy()
* agg()
* avg()
* sum()
* count()

## Date Functions

* to_date()
* month()
* year()
* datediff()

## Window Functions

* rank()
* dense_rank()
* lag()
* lead()

## Joins

* Inner joins
* Left joins
* Broadcast joins

## SQL

* createOrReplaceTempView()
* Spark SQL queries



# Learning Outcomes

Through this project I learned:

* Building ETL pipelines using PySpark
* Working with Medallion Architecture
* Distributed data processing using Spark
* Writing scalable analytical transformations
* Data cleaning techniques
* Window functions in Spark
* Joining multiple large datasets
* Using Databricks notebooks
* Creating analytics-ready business tables

---

# Future Improvements

Some improvements that can be added later:

* Add Airflow orchestration
* Add real-time streaming pipeline
* Add dashboard using Power BI or Tableau
* Add unit testing
* Dockerize the project
* Add CI/CD pipeline
* Partition Delta tables
* Add data quality framework

---

# Author

## Vivek Kumar Singh

LinkedIn:
[https://linkedin.com/in/vivek-singh04](https://linkedin.com/in/vivek-singh04)

GitHub:
[https://github.com/CodeVizk](https://github.com/CodeVizk)

---

# Repository

GitHub Repository:
[https://github.com/CodeVizk/olist-ecommerce-pyspark](https://github.com/CodeVizk/olist-ecommerce-pyspark)






























































# Olist E-Commerce Data Pipeline — PySpark + Databricks

## Overview
End-to-end data engineering pipeline built with PySpark on
Databricks to analyze the Brazilian Olist e-commerce dataset.
The pipeline ingests 9 relational CSV tables, performs
multi-table joins, cleaning, aggregations, and business
analytics using distributed computing.

---

## Dataset
**Brazilian E-Commerce Public Dataset by Olist**
Source: [Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

Curl Command- ```#!/bin/bash
curl -L -o ~/Downloads/brazilian-ecommerce.zip\
https://www.kaggle.com/api/v1/datasets/download/olistbr/brazilian-ecommerce```
9 tables — customers, orders, order items, products, sellers,
payments, reviews, geolocation, category translation

---

## Architecture
```

```

---

## Tech Stack
- **PySpark** — distributed data processing
- **Databricks** — serverless compute, notebooks
- **Apache Spark** — core engine
- **SQL / Spark SQL** — analytical queries
- **Python 3.x**

---

## Pipeline Steps


---

## Key Analysis Performed

---

## Environment Setup
This project runs on **Databricks Serverless Compute**.
No manual cluster setup required.

To run locally with PySpark:
```bash
pip install pyspark
```

---

## How to Run
1. Download Olist dataset from Kaggle
2. Upload CSVs to Databricks workspace
3. Open notebook and update file paths
4. Run cells sequentially

---

## Project Structure


---

## Key PySpark Concepts Used
- Multi-table joins with duplicate column handling
- Date transformations with `to_date()`, `year()`, `month()`
- GroupBy aggregations with `agg()`, `sum()`, `avg()`
- Window functions — `rank()`, `dense_rank()`, `lag()`, `lead()`
- Null handling — `fillna()`, `dropna()`
- Spark SQL with `createOrReplaceTempView()`

---

## Author
**Vivek Kumar Singh**
[LinkedIn](https://linkedin.com/in/vivek-singh04) |
[GitHub](https://github.com/CodeVizk)
