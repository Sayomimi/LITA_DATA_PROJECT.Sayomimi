# LITA_DATA_PROJECT.Sayomimi

## This is where I document my Data Analysis project.

### Project Title : Diamond quality and price analysis
---
[Project Overview](#project-overview)
[Data Sources](#data-sources)
[Tools Used](#tools-used)

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
Percentage of Cut

![Pie chart](https://github.com/user-attachments/assets/0476f19d-1928-4b5c-ab97-39a05b2abb6c)

Clarity by Max and Min prices

![MAX MIN DEPTH:CLARITY](https://github.com/user-attachments/assets/4fba3836-d369-4857-81db-38f39836a543)

Cut by Carat

![BAR CHART](https://github.com/user-attachments/assets/0974a303-66aa-4a41-a356-99504c291c14)

Average Price by Color

![LINE CHART AVG](https://github.com/user-attachments/assets/1832ca3a-664a-4237-ae7b-c0661f0175b0)

Total Clarity

![CLARITY LINE CHART](https://github.com/user-attachments/assets/f0ef405b-b468-41ef-8bc9-a1d03d31f1e2)

Depth by Price

![DEPTH LINE CHART](https://github.com/user-attachments/assets/98ab13f8-ae61-429e-b996-82ee65bdb004)



