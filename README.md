# Customer Shopping Behavior Analysis & Power BI Dashboard

End-to-end analysis of 3,900 customer purchase records using **SQL (PostgreSQL)**, **Excel** and **Power BI**.

## Business Questions
1. Which customers (male or female) generate more revenue?
2. Do subscribed customers spend more than non-subscribers?
3. How much do discounts affect purchases?
4. Which products are rated highest and which are discounted most?
5. How loyal are the customers, and which categories earn the most?

## Tools Used
- PostgreSQL / SQL: joins-free aggregations, subqueries, CTEs, window functions
- Excel: data cleaning and checks
- Power BI: interactive dashboard (DAX measures, Power Query)

## Dataset
- 3,900 rows, 18 columns (customer age, gender, item, category, purchase amount, season, review rating, subscription status, shipping type, discount applied, previous purchases, and more)
- File: `data/customer_shopping_behavior.csv`
- Source: [add the Kaggle / dataset link here]

## Data Cleaning
- Checked missing values: `Review Rating` had 37 missing values
- [Write how you handled them, for example "filled with the median rating of each category"]
- Renamed columns to snake_case for SQL
- Created `age_group` column [write your age ranges here]

## SQL Analysis (10 queries)
All queries are in `sql/customer_shopping_behavior.sql`.

| # | Question | SQL concepts |
|---|----------|--------------|
| Q1 | Revenue by gender | GROUP BY, SUM |
| Q2 | Discount users who spent above average | Subquery |
| Q3 | Top 5 products by average rating | AVG, ROUND, LIMIT |
| Q4 | Average spend: Standard vs Express shipping | WHERE IN, GROUP BY |
| Q5 | Subscribers vs non-subscribers | COUNT, AVG, SUM |
| Q6 | Top 5 products by discount rate | CASE WHEN |
| Q7 | Customer segments: New, Returning, Loyal | CTE, CASE WHEN |
| Q8 | Top 3 products in each category | CTE, ROW_NUMBER, PARTITION BY |
| Q9 | Do repeat buyers subscribe? | WHERE, GROUP BY |
| Q10 | Revenue by age group | GROUP BY, ORDER BY |

## Key Findings
- **Total revenue: $233,081.** Male customers brought **$157,890 (about 68%)** and female customers **$75,191 (about 32%)**.
- **Subscribers do not spend more.** 27% of customers are subscribers (1,053), and their average spend is **$59.49** vs **$59.87** for non-subscribers.
- **43% of all purchases used a discount.** Hat (50%), Sneakers (about 49.7%) and Coat (about 49.1%) have the highest discount rates.
- **Clothing earns the most revenue:** $104,264, about 45% of the total.
- **Most customers are loyal:** 3,116 of 3,900 (about 80%) are in the Loyal segment (more than 10 previous purchases).
- Highest-rated products: Gloves (3.86), Sandals (3.84), Boots (3.82).

## Dashboard
![Dashboard](images/dashboard.png)

File: `dashboard/customer_behavior_dashboard.pbix` (open with Power BI Desktop)

## Recommendations
- Review the subscription program, because subscribers spend about the same as non-subscribers.
- Test smaller discounts on products that already have a high discount rate.
- Promote Clothing and the top-rated products to grow revenue.

## How to Run
1. Create a table named `customer` in PostgreSQL and load `data/customer_shopping_behavior.csv`.
2. Run the queries in `sql/customer_shopping_behavior.sql`.
3. Open the `.pbix` file in Power BI Desktop to see the dashboard.

## Author
Neha Patil | [LinkedIn](https://linkedin.com/in/neha-patil-882a11257) | [GitHub](https://github.com/nehapatil1043-design)
