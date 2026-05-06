# CafeNoir_SQL_CaseStudy.
“SQL queries for analyzing sales, profit, and marketing data in a café case study.”

# CAFE_NOIR_DB – SQL Case Study

## Introduction
This project is a case study where I acted as a database administrator for a fictional café business.  
The goal was to analyze customer data, sales, profit, marketing spend, and product performance using SQL queries.  
I used three key datasets: **Fact**, **Product**, and **Location** tables.

## 🚀 My Approach
I created a database `CAFE_NOIR_DB` and wrote SQL queries to answer 29 specific business questions.  
Here are some highlights:

### 1️⃣ Number of States in Location Table
```Sql Query
SELECT COUNT(DISTINCT(State)) AS Total_States FROM Location;
```

### 2️⃣ Products of Regular Type
```
SELECT COUNT(Product) AS Product_Regular
FROM Product
WHERE Type='Regular';
```
### 3️⃣ Weekly Sales with ROLLUP
```
SELECT Sales, DENSE_RANK() OVER (ORDER BY Sales DESC) AS Sales_Rank
FROM fact;
```
### 4️⃣  User-Defined Function
```
CREATE FUNCTION dbo.GetbyProductType
(
    @Producttype NVARCHAR(50)
)
RETURNS TABLE
AS 
RETURN 
(
    SELECT ProductId, Product, Product_Type, Type
    FROM Product
    WHERE Product_Type = @Producttype
);
```
👉 Full queries are available in [queries.sql](queries.sql)
---
