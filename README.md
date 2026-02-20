# Kai & Karo Car Sales Analytics

**Branch:** Kiambu Road, Nairobi, Kenya  
**Data:** Cars, Salesmen, Customers, Sales transactions (60 sales entries)

## Overview
This database tracks car sales for Kai & Karo Car Sales Company, designed to support executive decision-making, KPI tracking, and business intelligence dashboards. The schema includes:

- Branches  
- Salesmen  
- Customers  
- Cars (brands, models, year of manufacture, cost in KES)  
- Sales transactions  

## Key Insights / BI Use Cases
- Total revenue per branch and overall  
- Revenue by car brand and model  
- Salesman performance ranking  
- Monthly revenue trends  
- Low stock alerts  

## Files
- `schema_and_data.sql` – Table structure + populated dataset  
- `analytics_queries.sql` – KPI and decision-making queries  
- `README.md` – Project description  

## Sample Queries
```sql
-- Total revenue
SELECT SUM(total_amount) AS total_revenue FROM sales;

-- Top selling cars
SELECT c.brand, c.model, SUM(s.quantity) AS units_sold
FROM sales s
JOIN cars c ON s.car_id = c.car_id
GROUP BY c.brand, c.model
ORDER BY units_sold DESC
LIMIT 10;
