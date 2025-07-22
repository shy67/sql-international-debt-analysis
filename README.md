# International Debt Analysis with SQL

This project explores global debt statistics using SQL and data based on World Bank reports.

## Objectives:
- Identify the number of unique countries with recorded debt  
- Determine the country with the highest total debt  
- Find the country with the lowest principal repayments  

## Skills Used:
- Data filtering and aggregation  
- Using COUNT, SUM, GROUP BY, ORDER BY  
- Basic financial data analysis  

## Full SQL Queries Used in the Project:

```sql
-- Number of unique countries  
SELECT COUNT(DISTINCT country_name) AS num_countries  
FROM international_debt;  

-- Country with the highest total debt  
SELECT country_name, SUM(debt) AS total_debt  
FROM international_debt  
GROUP BY country_name  
ORDER BY total_debt DESC  
LIMIT 1;  

-- Country with the lowest principal repayments  
SELECT country_name, indicator_name, debt AS lowest_repayment  
FROM international_debt  
WHERE indicator_code = 'DT.AMT.DLXF.CD'  
ORDER BY debt ASC  
LIMIT 1;  


