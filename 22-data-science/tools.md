# Analytics Tools

## Overview
Data Analysts are expected to be familiar with the modern data stack. This includes data warehousing (Snowflake, BigQuery), transformation tools (dbt), and BI/visualization tools (Tableau, Looker, PowerBI, Excel).

## Interview Questions

### Q1: Explain the purpose of a tool like dbt (data build tool) in a modern data stack.
**Difficulty:** Medium | **Frequency:** Increasing | **Companies:** Modern Tech Companies

**Excellent Answer:**
dbt is a transformation workflow that lets teams quickly and collaboratively deploy analytics code following software engineering best practices. It operates in the "T" of ELT (Extract, Load, Transform).
Instead of having messy, undocumented SQL scripts running via cron jobs, dbt allows analysts to write modular SQL `SELECT` statements. It handles dependencies, creates tables/views in the warehouse automatically, and allows for version control (Git), testing (e.g., asserting a column is unique and not null), and auto-generating documentation.

**Common Mistakes:**
- Confusing dbt with an ETL tool (dbt does not extract or load data; it only transforms data already in the warehouse).
- Not mentioning software engineering practices like version control or testing.

## Real-World Applications
- Migrating legacy Excel reporting into automated Looker dashboards powered by Snowflake.
- Using dbt to create a single source of truth "dim_customers" table for the whole company.

## Practice Problems

| Problem | Description | Difficulty | Link |
|---|---|---|---|
| Tool Comparison | Compare Tableau vs Looker architecture | Easy | [Link](#) |
| Excel Mastery | Explain VLOOKUP vs INDEX/MATCH | Easy | [Link](#) |

## Hiring Manager Perspective
While tools can be learned, I want to see if the candidate understands the *ecosystem*. Do they know why we use a columnar database like Redshift for analytics instead of Postgres? Do they appreciate data governance?

## AI Interview Coach
**ChatGPT/Claude/Gemini Prompts:**
- "Quiz me on the differences between ETL and ELT architectures."
- "What are the most common Tableau interview questions?"
