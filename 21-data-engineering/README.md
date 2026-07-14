# Data Engineering Overview

## Overview
Data Engineering focuses on the practical application of data collection, storage, and processing. It bridges the gap between software engineering and data science, building the infrastructure that allows organizations to analyze massive datasets reliably.

## Interview Questions
**Question:** What is the difference between an ETL and an ELT process?
- **Difficulty/Frequency/Companies:** Easy / Very High / Snowflake, Databricks, Uber
- **Excellent Answer:** ETL (Extract, Transform, Load) transforms data in a staging server before loading it into the data warehouse. ELT (Extract, Load, Transform) loads raw data directly into the warehouse and uses the warehouse's compute power to transform it. ELT is increasingly popular due to powerful cloud data warehouses like Snowflake.
- **Common Mistakes:** Mixing up the order or not understanding why modern cloud architecture favors ELT.

## Real-World Applications
- **Recommendation Systems:** Processing user behavior logs nightly to train new ML models.
- **Financial Reporting:** Aggregating billions of daily transactions into clean, verified tables for analysts.

## Practice Problems

| Problem Name | Type | Difficulty | Focus Area |
| --- | --- | --- | --- |
| Design an Analytics Pipeline | System Design | Hard | End-to-end Architecture |
| Handle Late-Arriving Data | Concept | Medium | Data Consistency |
| Data Quality Validation | Architecture | Medium | Testing & Alerting |

## Hiring Manager Perspective
I look for a strong software engineering foundation (Python/Scala/SQL) combined with a deep understanding of distributed systems, big data formats (Parquet, ORC), and pipeline orchestration.

## AI Interview Coach Prompts
- **ChatGPT:** "Act as a Data Engineering Hiring Manager. Ask me a broad architectural question about building a data platform from scratch."
- **Claude:** "Give me a scenario involving a failing data pipeline and ask me how I would debug and backfill the missing data."
- **Gemini:** "Quiz me on the trade-offs between batch and stream processing for different business use cases."
