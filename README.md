# Superstore Sales & Profitability Analysis
Analyzing retail performance through SQL to drive business growth and margin optimization.
## Project Overview
This project explores a multi-year retail dataset to identify high-performing products, profitable regions, and the impact of pricing strategies. Using SQL, I transformed raw transactional data into business intelligence to help stakeholders understand where to invest and where to cut costs.
## Dataset Used
[Superstore Sales Dataset](https://github.com/TuiyaVictoria/revenue-insight-analysis/blob/main/SampleSuperstore.csv)

### Key Business Questions
1. Profitability: Which products are "Loss Leaders" (high sales but negative profit)?
2. Operations: How does shipping mode and regionality affect the bottom line?
3. Strategy: At what percentage does a discount stop driving growth and start destroying profit?
### Analysis Deep Dive
1.High-Level Performance
The first step was establishing the total health of the business by calculating total revenue and total profit.
SELECT 
    ROUND(SUM(sales), 2) AS total_revenue,
    ROUND(SUM(profit), 2) AS total_profit
FROM 'SampleSuperstore.csv';
2.Category Insights
I analyzed sales by category to see which business units lead the market.

3.The Discount Impact (Crucial Finding)
By grouping data by discount levels, I identified the threshold where discounts become detrimental to the business.
SELECT 
    Discount, 
    AVG(Profit) AS avg_profit, 
    SUM(Sales) AS total_sales
FROM 'SampleSuperstore.csv'
GROUP BY Discount
ORDER BY Discount;
