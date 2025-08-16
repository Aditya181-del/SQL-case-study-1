# 🧠 SQL Business Intelligence Case Study – Retail Data Analysis (Jan 2025)

This project demonstrates **SQL-driven business intelligence** using structured retail data across three tables: **FACT, PRODUCT, and LOCATION**. The goal was to derive insights on **sales, profit, inventory, and marketing** using advanced SQL queries and BI-style logic.

---

## 🎯 Objectives
- Analyze product performance across regions.  
- Track sales, profit, inventory, and marketing spend.  
- Apply advanced SQL (procedures, roll-ups, transactions) for business insights.  

---

## 📂 Files
- `CASE STUDY 24FEB.sql` → 25+ SQL queries, stored procedures, user-defined functions, and transactions.  

---

## 🗂️ Data Schema
- **FACT Table:** Date, ProductID, Sales, COGS, Profit, Expenses, Marketing, Area_Code, Inventory.  
- **PRODUCT Table:** ProductID, Product_Type, Product_Name.  
- **LOCATION Table:** Area_Code, State.  

---

## 🔍 Sample Business Questions Answered
- Total number of unique states in dataset.  
- State-wise **sales & profit aggregation**.  
- Top product types by profitability.  
- Weekly sales trends using `GROUP BY ROLLUP`.  
- Average inventory per product.  
- Stored procedure to filter products by type.  
- Classify profit/loss by expense level (CASE logic).  
- Joins, UNION, INTERSECT on Area Codes.  

---

## ⚙️ SQL Concepts Used
- Joins (INNER, CROSS)  
- Aggregations (SUM, AVG, MIN, MAX)  
- GROUP BY ROLLUP  
- Ranking (`DENSE_RANK`)  
- CASE statements (conditional logic)  
- Stored Procedures & Transactions (BEGIN, ROLLBACK)  
- User-Defined Functions (UDFs)  

---

## 📎 About Me
I’m **Aditya Tirakapadi**, a student of AI & Data Science with interests in data visualization, trend analysis, and business insights from real-world datasets.

- 💼 [GitHub](https://github.com/Aditya181-del)  
- 🔗 [LinkedIn](https://www.linkedin.com/in/aditya-tirakapadi-90a38b26b/)  

---

⭐ If you find this project helpful, please **star** the repo or fork it for your own exploration!

## 💡 Example Queries
```sql
-- Total profit from Colorado
SELECT SUM(PROFIT)
FROM FACT
JOIN LOCATION ON FACT.AREA_CODE = LOCATION.AREA_CODE
WHERE STATE = 'Colorado';

-- Rank products by sales
SELECT *, DENSE_RANK() OVER(ORDER BY SALES DESC) AS SALES_RANK 
FROM FACT;
