
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
