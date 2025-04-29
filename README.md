# TASK6-DATA-ANALYSIS
SQL TASK
# 📊 Task 6: Sales Trend Analysis Using Aggregations

## 🎯 Objective
Analyze monthly revenue and order volume from the `online_sales` dataset.

## 🧰 Tools
- MySQL / PostgreSQL / SQLite

## 📂 Dataset
Table: `orders`  
Columns: `order_date`, `amount`, `product_id`, `order_id`

## 📌 SQL Query

```sql
SELECT
    EXTRACT(YEAR FROM order_date) AS year,
    EXTRACT(MONTH FROM order_date) AS month,
    SUM(amount) AS total_revenue,
    COUNT(DISTINCT order_id) AS order_volume
FROM
    orders
WHERE
    order_date BETWEEN '2024-01-01' AND '2024-04-30'
GROUP BY
    year, month
ORDER BY
    year, month;

