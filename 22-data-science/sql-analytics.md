# SQL for Analytics

## Overview
For data analysts, SQL is the primary tool for data extraction and transformation. Interviews require mastery of aggregations, date/time functions, string manipulations, window functions, and handling complex business logic within queries.

## Interview Questions

### Q1: Write a query to calculate the 7-day rolling average of daily active users (DAU).
**Difficulty:** Medium-Hard | **Frequency:** Very High | **Companies:** Slack, Zoom, Twitter

**Excellent Answer:**
Assuming a table `user_logins` with `login_date` and `user_id`:

```sql
WITH daily_counts AS (
    SELECT login_date, COUNT(DISTINCT user_id) as dau
    FROM user_logins
    GROUP BY login_date
)
SELECT 
    login_date,
    dau,
    AVG(dau) OVER (
        ORDER BY login_date 
        ROWS BETWEEN 6 PRECEDING AND CURRENT ROW
    ) as rolling_7d_avg
FROM daily_counts;
```
This uses a CTE to first get daily unique counts, and then applies a window function to calculate the average over the current row and the 6 preceding rows.

**Common Mistakes:**
- Forgetting to use `COUNT(DISTINCT)` to get DAU.
- Using `ROWS BETWEEN 7 PRECEDING` (which actually averages 8 days).

## Real-World Applications
- Identifying drop-off points in a user registration funnel.
- Calculating Year-over-Year (YoY) revenue growth per region.

## Practice Problems

| Problem | Description | Difficulty | Link |
|---|---|---|---|
| Sessionization | Group user events into 30-minute sessions | Hard | None |
| Cumulative Sum | Calculate running total of revenue by month | Medium | None |

## Hiring Manager Perspective
Can the candidate write readable, maintainable SQL? I look for good formatting, proper use of CTEs instead of deeply nested subqueries, and a solid understanding of edge cases (like how to handle days with zero logins).

## AI Interview Coach
**ChatGPT/Claude/Gemini Prompts:**
- "Generate a complex SQL question involving self-joins and date math."
- "Review this SQL query and suggest ways to optimize its performance."
