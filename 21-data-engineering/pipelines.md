# Data Pipelines & Orchestration

## Overview
Data pipelines are the plumbing of the data world, moving data from source to destination while filtering, cleaning, and aggregating it. Orchestration tools (like Airflow, Dagster, Prefect) manage the scheduling, execution, and monitoring of these complex workflows.

## Interview Questions
**Question:** How would you design a data pipeline to ensure idempotency, and why is it important?
- **Difficulty/Frequency/Companies:** Medium / High / Airbnb, Netflix, Spotify
- **Excellent Answer:** Idempotency means a pipeline can be run multiple times with the same input and produce the exact same final state without duplicating data. It's critical for backfilling or retrying failed jobs. I'd design it by using "upserts" (MERGE statements) instead of simple inserts, or by always deleting the target partition before writing new data into it.
- **Common Mistakes:** Not knowing what idempotency is, or suggesting solutions that only work for happy paths (like just appending data).

## Real-World Applications
- **Log Processing:** Ingesting server logs into a data lake, partitioned by hour.
- **Marketing Automation:** Syncing user segmentation data from a warehouse to third-party marketing tools via reverse ETL.

## Practice Problems

| Problem Name | Type | Difficulty | Focus Area |
| --- | --- | --- | --- |
| DAG Design for Dependencies | Architecture | Medium | Airflow/Orchestration |
| Backfilling Strategy | Concept | Hard | Data consistency |
| Handling Schema Changes | Pipeline Design | Hard | Schema Evolution |

## Hiring Manager Perspective
Candidates must demonstrate how they handle failure. Pipelines will fail. Can they build resilient pipelines that alert appropriately, retry gracefully, and don't duplicate data upon recovery?

## AI Interview Coach Prompts
- **ChatGPT:** "Give me a complex DAG scenario with multiple dependencies. Ask me how I would optimize its execution and handle failures in the middle of the graph."
- **Claude:** "Ask me to explain idempotency in data pipelines and require me to provide code or pseudo-code to achieve it."
- **Gemini:** "Roleplay an interview discussing the migration from cron-based scripts to Apache Airflow. What are the benefits and challenges?"
