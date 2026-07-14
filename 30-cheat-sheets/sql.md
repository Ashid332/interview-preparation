# SQL Cheat Sheet

## Key Concepts
| Concept | Description |
|---|---|
| ACID Properties | Atomicity, Consistency, Isolation, Durability — guarantee database transactions are processed reliably. |
| Indexes | Data structures that improve the speed of data retrieval operations. |
| Normalization | Organizing data to reduce redundancy and improve data integrity (1NF, 2NF, 3NF). |
| Joins | Combining rows from two or more tables based on a related column (INNER, LEFT, RIGHT, FULL). |

## Must-Know Items
- Primary Keys vs Foreign Keys.
- Aggregation functions (`GROUP BY`, `HAVING`).
- Window functions (`ROW_NUMBER()`, `RANK()`, `OVER()`).
- Query execution order (FROM -> WHERE -> GROUP BY -> HAVING -> SELECT -> ORDER BY).

## Common Interview Questions (Quick)
1. Difference between `WHERE` and `HAVING`.
2. Difference between `INNER JOIN` and `LEFT JOIN`.
3. What is an index? What are its drawbacks?
4. Explain the difference between `DELETE`, `TRUNCATE`, and `DROP`.
5. Find the second highest salary from an Employee table.

## Critical Commands/Patterns
```sql
-- Window Function Pattern (Top N per category)
WITH RankedData AS (
  SELECT department, employee, salary,
         RANK() OVER (PARTITION BY department ORDER BY salary DESC) as rank
  FROM Employees
)
SELECT * FROM RankedData WHERE rank <= 3;

-- Aggregation with Having
SELECT department, COUNT(*) 
FROM Employees 
GROUP BY department 
HAVING COUNT(*) > 10;
```

## Decision Framework
- **Indexing:** Add indexes on columns frequently used in `WHERE`, `JOIN`, and `ORDER BY` clauses. Avoid over-indexing as it slows down `INSERT`/`UPDATE` operations.
- **Normalization vs Denormalization:** Normalize for write-heavy systems (OLTP) to avoid anomalies. Denormalize for read-heavy systems (OLAP) to speed up reads by avoiding complex joins.

## Common Mistakes
- Using `SELECT *` instead of specifying required columns.
- Forgetting that `NULL` comparisons require `IS NULL` or `IS NOT NULL`, not `=` or `!=`.
- Joining large tables without appropriate indexes.
- Not using parameterized queries in application code (leading to SQL injection).

## One-Minute Review
- Master Joins, Grouping, and Window Functions. Understand how databases physically execute queries to reason about performance and indexing.
