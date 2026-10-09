# Customer Segmentation using RFM Analysis

An interactive Power BI dashboard that segments 18,484 customers by their purchasing behavior using RFM (Recency, Frequency, Monetary) analysis, and recommends a marketing action for each segment.

![Dashboard](customer%20segmentation.png)

## Dataset
AdventureWorks DW (Microsoft sample database): internet sales from July 2005 to July 2008, with 27,659 orders and $29.36M in revenue.

## Approach
1. **Data preparation (Power Query):** loaded sales, customer and geography tables, promoted headers, removed duplicate score mappings, merged first and last name.
2. **RFM metrics (DAX):** for each customer, Recency = days since last order, Frequency = number of orders, Monetary = total spend.
3. **Scoring (1-5):** Recency and Monetary scored by quintiles using PERCENTILE.INC. Frequency scored by order count (1, 2, 3, 4, 5+) because 63% of customers placed only one order, so quintiles were not meaningful.
4. **Segmentation:** the combined RFM score (e.g. 545) is mapped to one of 11 segments such as Champions, Loyal, At Risk and Lost Customers.
5. **Dashboard:** KPI cards, customers and revenue by segment, segment behavior table, marketing recommendations, customers by country, with slicers for country and segment.

## Key Insights
- **Champions** are only 63 customers but spend the most on average ($8,258 each, about 8 orders).
- **At Risk** customers (1,807) generated $7.9M in revenue but have not purchased for 283 days on average. Winning them back is the biggest opportunity.
- **Promising** is the largest segment (4,605 customers, $8.7M revenue).
- **New Customers** are the second largest group (3,419) but spend very little so far ($38 on average).
- **Cannot Lose Them** customers (1,798) were valuable but have been inactive for 439 days on average.

## Recommendations
- Run win-back offers for At Risk and Cannot Lose Them customers first.
- Reward Champions and Loyal customers with loyalty programs and early access.
- Nurture New and Promising customers with onboarding and repeat-purchase incentives.

## Tools
Power BI, Power Query, DAX, Excel
