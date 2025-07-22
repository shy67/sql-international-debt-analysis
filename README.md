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
``` 


## Key Findings

- The dataset contains **124** unique countries with recorded debt.  
- **China** had the highest total debt in this dataset, totaling approximately **$285.79 billion USD**.  
- **Timor-Leste** had the lowest principal repayments, with an amount of about **$825,000 USD**.  

These figures provide a snapshot of international debt levels, but they may not fully reflect global totals due to limitations in the dataset.

## Data Source & Disclaimer

This data comes from a project I completed using a dataset based on World Bank reports, made available through an educational platform. The dataset may only include specific types of debt or cover a limited timeframe. For example, while this dataset shows China’s debt as around $285 billion, other sources report figures in the trillions. That difference likely comes from variations in what types of debt are included, how they’re defined, and the time period covered.

## What I Learned

This project helped me improve my SQL skills and think critically about real world data. I practiced writing queries to filter, group, and analyze financial information, and I gained insight into how countries manage debt. It also taught me the importance of understanding a dataset’s scope and limitations, not just trusting the numbers at face value, but asking what they really represent.

