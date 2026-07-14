# SQL for Data Science

## Overview
SQL is arguably the most important skill for a data scientist. You must be able to retrieve, clean, and aggregate data independently. Interviews focus heavily on complex joins, window functions (LEAD, LAG, RANK), subqueries, and CTEs.

## Interview Questions

### Q1: Explain the difference between WHERE and HAVING.
**Difficulty:** Easy | **Frequency:** Very High | **Companies:** All

**Excellent Answer:**
Both are used to filter records, but they operate at different stages of the query execution.
- **WHERE** filters individual rows *before* any groupings or aggregations take place. You cannot use aggregate functions (like SUM or COUNT) in a WHERE clause.
- **HAVING** filters groups *after* the GROUP BY clause and aggregations have been applied. It is specifically designed to be used with aggregate functions.
For example, if you want to find customers who made a purchase in 2023, you use `WHERE year = 2023`. If you want to find customers who made *more than 5* purchases in 2023, you use `HAVING COUNT(purchase_id) > 5`.

**Common Mistakes:**
- Saying HAVING is just a replacement for WHERE.
- Confusing the order of execution (FROM -> WHERE -> GROUP BY -> HAVING -> SELECT).

## Real-World Applications
- Calculating a 30-day rolling average of daily active users using Window Functions.
- Finding the top 3 highest-spending customers in each region using `DENSE_RANK()`.

## Practice Problems

| Problem | Description | Difficulty | Link |
|---|---|---|---|
| Nth Highest Salary | Find the Nth highest salary using dense_rank | Medium | [Link](#) |
| Retention Curve | Write a query to calculate Month-over-Month retention | Hard | [Link](#) |

## Hiring Manager Perspective
If a data scientist cannot write complex SQL, they will constantly block on data engineering teams to get the data they need. I look for fluency in CTEs and window functions, and an understanding of query optimization.

## AI Interview Coach
**ChatGPT/Claude/Gemini Prompts:**
- "Provide a complex database schema for an e-commerce site and ask me 3 hard SQL questions utilizing Window Functions."
- "Explain the difference between a LEFT JOIN and an INNER JOIN with a Venn diagram description."
