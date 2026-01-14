<div align="center">

#  SQL Analytics Portfolio

[![SQL](https://img.shields.io/badge/SQL-PostgreSQL_&_MySQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)](https://postgresql.org)
[![Queries](https://img.shields.io/badge/Queries-50+-success?style=for-the-badge)]()
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](LICENSE)

**Production-ready SQL queries solving real business analytics problems**

[Week 1: Foundations](week1_foundations/)  [Week 2: Optimization](week2_optimization/)  [Projects](projects/)  [LeetCode](leetcode_solutions/)

</div>

---

##  Skills Demonstrated

| Skill | Queries | Complexity | Status |
|-------|---------|------------|--------|
| Advanced JOINs & Set Operations | 15 |  |  Complete |
| Window Functions | 12 |  |  Complete |
| CTEs & Subqueries | 10 |  |  Complete |
| Performance Optimization | 8 |  |  In Progress |

---

##  Featured Query Examples

### Month-over-Month Revenue Growth
```sql
WITH monthly_revenue AS (
    SELECT 
        DATE_TRUNC('month', order_date) AS month,
        SUM(order_total) AS revenue
    FROM orders
    GROUP BY 1
)
SELECT 
    month,
    revenue,
    LAG(revenue) OVER (ORDER BY month) AS prev_month,
    ROUND((revenue - LAG(revenue) OVER (ORDER BY month)) / 
          LAG(revenue) OVER (ORDER BY month) * 100, 2) AS growth_pct
FROM monthly_revenue;
```

### Customer Lifetime Value by Cohort
```sql
WITH customer_cohorts AS (
    SELECT 
        customer_id,
        DATE_TRUNC('month', MIN(order_date)) AS cohort_month
    FROM orders
    GROUP BY customer_id
)
SELECT 
    c.cohort_month,
    COUNT(DISTINCT c.customer_id) AS cohort_size,
    SUM(o.order_total) AS total_revenue,
    ROUND(SUM(o.order_total) / COUNT(DISTINCT c.customer_id), 2) AS avg_ltv
FROM customer_cohorts c
JOIN orders o ON c.customer_id = o.customer_id
GROUP BY c.cohort_month
ORDER BY c.cohort_month;
```

---

##  Repository Structure

```
sql-analytics-portfolio/
 week1_foundations/           # Core SQL concepts
    day1_advanced_joins.sql
    day2_window_functions.sql
    day3_cte_subqueries.sql
 week2_optimization/          # Performance tuning
 projects/
    ecommerce_analysis/      # Revenue & customer analytics
    customer_segmentation/   # RFM segmentation
 leetcode_solutions/          # Coding challenges
 LICENSE
 README.md
```

---

##  LeetCode Progress

| Difficulty | Solved | Target |
|------------|--------|--------|
|  Easy | 0 | 50 |
|  Medium | 0 | 30 |
|  Hard | 0 | 20 |

**Goal:** 100+ problems in 30 days

---

##  Weekly Learning Log

### Week 1: SQL Foundations 
- **Day 1:** Advanced JOINs & Set Operations (15 queries)
- **Day 2:** Window Functions Mastery (12 queries)
- **Day 3:** CTEs & Subqueries (10 queries)

### Week 2: Optimization 
- **Day 1:** Query Execution Plans
- **Day 2:** Indexing Strategies
- **Day 3:** Performance Tuning

---

##  Projects

### 1. E-Commerce Analysis
> Analyze customer behavior, product performance, and revenue trends

- **Database:** PostgreSQL
- **Techniques:** JOINs, Window Functions, CTEs
- **Status:**  Complete

### 2. Customer Segmentation
> RFM (Recency, Frequency, Monetary) customer segmentation

- **Database:** PostgreSQL
- **Techniques:** CASE expressions, Aggregations
- **Status:**  In Progress

---

##  Connect

-  **Portfolio:** [amaninsights.vercel.app](https://amaninsights.vercel.app)
-  **LinkedIn:** [linkedin.com/in/aman2805](https://www.linkedin.com/in/aman2805)
-  **GitHub:** [github.com/amaninsights](https://github.com/amaninsights)

---

<div align="center">

** Star this repo if you found it helpful!**

*Last Updated: January 2026*

</div>
