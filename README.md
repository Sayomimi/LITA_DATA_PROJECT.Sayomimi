# LITA_DATA_PROJECT.Sayomimi

## This is where I document my Data Analysis project.

### Project Title : Diamond quality and price analysis
---
### Project Overview
This project analyzes diamond characteristics and pricing trends using SQL and Excel to uncover relationships quality attributes and prices.
-
### Data Sources
The primary source id diamond.cvs which can be downloaded from an open data source such as kaggle.
---
### Tools Used
- Mircosoft Excel for pivot table and visualization [Download Here](https://www.microsoft.com)
- SQL - Structured Query Language for querying the data
- Git Hub for portfolio building
---
### Data Preparations
The initial phase of the Data preparation, I performed the following action;
1. Data loading and inspection
2. Data dupication
3. Altering data types
4. Ensuring data consistency for analysis
---
### Exploratory Data Analysis
EDA includes summarizing
- The attributes
- Grouping by categories
- Calculating averages
- Identifying correlations between variables.
---
### Data Analysis
Codes used during my analysis
```SQL
CREATE DATABASE Diamond_DB;
USE Diamond_DB;
--Insert the diamonds_table- -

SELECT * FROM diamonds;

CREATE TABLE temp_table LIKE diamonds;
INSERT INTO temp_table SELECT * FROM diamonds;

ALTER TABLE temp_table RENAME diamonds_dup;

SELECT * FROM diamonds_dup;

ALTER TABLE diamonds_dup
CHANGE MyUnknownColumn id INT;

ALTER TABLE diamonds_dup
 MODIFY price DECIMAL(10, 2);

SELECT 
MIN(price) AS Minimum_price, 
carat AS Carat, 
MAX(price) AS Maximum_price 
FROM diamonds_dup
GROUP BY Carat;

SELECT color, cut, AVG(price) AS avg_price
FROM diamonds_dup
GROUP BY cut,color
ORDER BY avg_price;

SELECT * FROM diamonds_dup
WHERE carat >= '0.3' AND cut = 'Premium'
ORDER BY color;
```
---
### Data Visualization
Count of cut
![Pie chart](https://github.com/user-attachments/assets/0476f19d-1928-4b5c-ab97-39a05b2abb6c)

Clarity by Max and Min prices
![Line Chart](https://github.com/user-attachments/assets/ef1998a7-43f1-4bfb-91c4-df451388cfc0)

