# Relational Databases & SQL

## Overview
SQL (Structured Query Language) and relational databases (RDBMS) like PostgreSQL and MySQL manage structured data using tables with predefined schemas. They excel in complex queries, strict data integrity, and transactions.

## Interview Questions
**Question:** Explain the difference between Clustered and Non-Clustered Indexes.
- **Difficulty/Frequency/Companies:** Medium / High / Microsoft, Amazon, Stripe
- **Excellent Answer:** A clustered index determines the physical order of data in a table, so there can be only one per table. A non-clustered index stores a separate structure pointing to the actual data rows, allowing multiple non-clustered indexes per table. Clustered is faster for range queries, while non-clustered is good for exact matches on non-primary keys.
- **Common Mistakes:** Saying non-clustered indexes contain the actual data, or forgetting the performance trade-offs during write operations.

## Real-World Applications
- **Financial Systems:** Transactions, ledger processing where ACID is non-negotiable.
- **ERP Systems:** Highly structured business data requiring complex joins and reporting.

## Practice Problems

| Problem Name | Type | Difficulty | Focus Area |
| --- | --- | --- | --- |
| Nth Highest Salary | SQL Query | Medium | Window Functions |
| Department Top Three Salaries | SQL Query | Hard | JOINs, Subqueries |
| Index Optimization | Database Tuning | Hard | Execution Plans |

## Hiring Manager Perspective
Candidates should demonstrate strong query writing skills (especially JOINs, GROUP BY, and window functions) and understand query execution plans, indexing strategies, and locking mechanisms.

## AI Interview Coach Prompts
- **ChatGPT:** "Generate 3 advanced SQL query challenges focusing on window functions and CTEs. Provide sample schemas."
- **Claude:** "Act as a DBA. I will describe an indexing strategy for a highly contested table. Tell me why my strategy might fail."
- **Gemini:** "Ask me theoretical questions about isolation levels and anomalies (dirty read, phantom read) in SQL databases."
