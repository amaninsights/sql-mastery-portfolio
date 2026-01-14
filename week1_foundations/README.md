# Week 1: SQL Foundations

## Day 1: Advanced JOINs & Set Operations

### Learning Objectives
- Master all 7 types of JOINs
- Understand when to use each JOIN type
- Write production-quality analytical queries
- Handle NULL values and edge cases

### Queries Overview

#### Basic JOINs (Queries 1-3)
- **Q1:** Orders with customer information (INNER JOIN)
- **Q2:** All products with sales data (LEFT JOIN)
- **Q3:** Products never ordered (Anti-JOIN pattern)

#### Aggregation & Analytics (Queries 4-7)
- **Q4:** Revenue by city with CTEs (⭐ Used CTE for clarity)
- **Q5:** Electronics customers (Multi-table INNER JOIN)
- **Q6:** Seller performance including zero sales (LEFT JOIN + COALESCE)
- **Q7:** Products sold in specific city (4-table JOIN)

#### Advanced Patterns (Queries 8-10)
- **Q8:** Multi-seller customers (GROUP BY + HAVING with DISTINCT)
- **Q9:** Review scores by category (Optimized 3-table join)
- **Q10:** Electronics but NOT Books customers (Anti-JOIN)

#### Expert Level (Queries 11-15)
- **Q11:** Product pairs bought together (SELF JOIN) ⭐
- **Q12:** Customer lifetime value by state (NULL handling)
- **Q13:** Orphan data detection (FULL OUTER JOIN) ⭐
- **Q14:** Month-over-month growth (Time-series, 2 methods) ⭐⭐
- **Q15:** Product-seller matrix (CROSS JOIN + analysis) ⭐

### Key Learnings
1. **COUNT vs COUNT(DISTINCT):** Critical for multi-seller analysis
2. **Anti-JOIN patterns:** Three methods (LEFT JOIN + NULL, NOT EXISTS, EXCEPT)
3. **Query optimization:** Removing unnecessary table joins (Query 9)
4. **Time-series:** Self-join vs Window functions for MoM growth
5. **CROSS JOIN use cases:** Gap analysis and opportunity identification

### Business Impact
These queries solve real business problems:
- Customer segmentation for targeted marketing
- Product recommendation systems (market basket)
- Revenue analysis for budget allocation
- Data quality monitoring (orphan detection)
- Growth tracking for executive reporting

### Challenges Overcome
- Understanding when to use DISTINCT in aggregations
- Handling year rollover in time-series calculations
- Optimizing multi-table JOIN sequences

### Next Steps
- Day 2: Window Functions deep dive
- Apply these patterns to real 100k+ row dataset

---
[View SQL File →](./day1_advanced_joins.sql)
