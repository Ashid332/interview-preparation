# SQL Quick Reference

## Order of Execution
1.  `FROM` (and `JOIN`)
2.  `WHERE`
3.  `GROUP BY`
4.  `HAVING`
5.  `SELECT`
6.  `ORDER BY`
7.  `LIMIT` / `OFFSET`

## Joins
*   **INNER JOIN:** Returns records that have matching values in both tables.
*   **LEFT (OUTER) JOIN:** Returns all records from the left table, and matched records from the right (or NULL).
*   **RIGHT (OUTER) JOIN:** Returns all records from the right table, and matched records from the left (or NULL).
*   **FULL (OUTER) JOIN:** Returns all records when there is a match in either left or right table.
*   **CROSS JOIN:** Returns the Cartesian product of the sets of records from the two joined tables.

## Aggregate Functions & Grouping
*   `COUNT()`, `SUM()`, `AVG()`, `MIN()`, `MAX()`.
*   *Rule:* Any column in `SELECT` that is not part of an aggregate function MUST be in the `GROUP BY` clause.
*   Use `WHERE` to filter rows *before* aggregation. Use `HAVING` to filter groups *after* aggregation.

## Window Functions (Advanced Analytics)
Perform calculations across a set of table rows related to the current row.
```sql
SELECT 
    employee_id,
    department,
    salary,
    -- Rank employees by salary within each department
    RANK() OVER (PARTITION BY department ORDER BY salary DESC) as dept_rank,
    -- Running total of salary within department
    SUM(salary) OVER (PARTITION BY department ORDER BY employee_id) as running_total
FROM employees;
```

## Common Gotchas
*   `NULL` comparisons: Use `IS NULL` or `IS NOT NULL`. `column = NULL` is always false.
*   `COUNT(*)` counts rows including NULLs. `COUNT(column_name)` counts non-NULL values.
*   `UNION` removes duplicates. `UNION ALL` keeps duplicates (and is faster).
