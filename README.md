# 🧠 SQL Business Intelligence Case Study – Retail Data Analysis (Jan 2025)

This project showcases a **real-world SQL case study** involving data analysis over three structured tables: `FACT`, `PRODUCT`, and `LOCATION`. The goal is to derive business insights from sales, marketing, and inventory data using core and advanced SQL techniques.

---

## 📂 Files Included

| File | Description |
|------|-------------|
| `CASE STUDY 24FEB.sql` | SQL script containing 25+ analytical queries, procedures, functions, and transactions |

---

## 🧠 Objective

- Analyze product performance across regions
- Track sales, profit, inventory, and marketing expenses
- Apply advanced SQL logic to solve real business problems
- Use stored procedures and roll-ups for BI-like queries

---

## 🗂️ Data Schema Overview

1. **FACT Table** – Contains transaction-level data like:
   - `DATE`, `PRODUCTID`, `SALES`, `COGS`, `PROFIT`, `TOTAL_EXPENSES`, `MARKETING`, `AREA_CODE`, `INVENTORY`

2. **PRODUCT Table** – Contains product metadata:
   - `PRODUCTID`, `PRODUCT_TYPE`, `PRODUCT`, `TYPE`

3. **LOCATION Table** – Maps area codes to states:
   - `AREA_CODE`, `STATE`

---

## 🔍 Business Questions Solved

✅ A selection of the 25+ business questions answered in SQL:

1. How many unique states are present in the dataset?
2. What is the total marketing spend for Product ID 1?
3. Which product types generate the most profit?
4. State-wise sales and profit aggregation
5. Weekly sales trends using `ROLLUP`
6. Inventory averages per product
7. Stored procedures to filter by product type
8. Conditional logic (e.g., classify profit/loss by expense level)
9. ASCII and substring functions on product names
10. Use of `UNION` and `INTERSECT` on `AREA_CODE`

---

## ⚙️ Key SQL Concepts Used

- Joins (INNER JOIN, CROSS JOIN)
- Aggregation (SUM, AVG, MIN, MAX)
- Grouping & `GROUP BY ROLLUP`
- Ranking using `DENSE_RANK`
- Conditional logic using `CASE`
- Stored Procedures
- Transactions with `BEGIN`, `ROLLBACK`
- User-Defined Functions (UDFs)

---

## 💡 Example Highlight Queries

```sql
-- Total profit from Colorado state
SELECT SUM(PROFIT)
FROM FACT
JOIN LOCATION ON FACT.AREA_CODE = LOCATION.AREA_CODE
WHERE STATE = 'Colorado';

-- Rank products by sales
SELECT *, DENSE_RANK() OVER(ORDER BY SALES DESC) AS SALES_RANK FROM FACT;

-- Procedure to filter products by type
CREATE PROCEDURE PR_1(@PRODUCTTYPE NVARCHAR(70))
AS
BEGIN
    SELECT * FROM PRODUCT
    WHERE @PRODUCTTYPE = Product_Type
END;
