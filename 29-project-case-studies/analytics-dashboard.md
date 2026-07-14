# Analytics Dashboard Case Study

## Problem
A SaaS company needs an internal dashboard to track business metrics (Active Users, Revenue, Error Rates) in near real-time, aggregating data from multiple microservices and databases.

## Requirements
* **Functional:**
  * View time-series data (e.g., daily active users over the last 30 days).
  * Slice and dice data by various dimensions (region, device type, subscription tier).
  * Export reports.
* **Non-Functional:**
  * Queries must return in under 2 seconds.
  * System must ingest billions of events per day.
  * Data must be accurate and eventually consistent.

## Architecture
1. **Event Publishers:** Various microservices emit telemetry and business events.
2. **Message Broker:** Kafka acts as the central nervous system, buffering all events.
3. **ETL/ELT Pipeline:** Workers consume Kafka topics, clean the data, and enrich it.
4. **OLAP Database (Data Warehouse):** A columnar database designed specifically for fast analytical queries (e.g., ClickHouse, Snowflake, Redshift).
5. **Dashboard API:** Serves query results to the frontend.
6. **Frontend:** React application using charting libraries (e.g., Recharts, D3.js).

## Trade-offs
* **OLTP vs OLAP:** We cannot run these massive aggregation queries on our primary application databases (OLTP) without crashing them. We trade architectural simplicity for performance by replicating data into a specialized OLAP database, accepting some replication latency.
* **Pre-aggregation vs Raw Data:** Storing raw data allows infinite flexibility in slicing and dicing, but querying it is slow. Pre-aggregating data (e.g., rolling up hourly stats into daily stats) makes dashboards lightning fast but loses granular detail. We do both: keep raw data in cold storage and pre-aggregate hot data in the OLAP database.

## Scaling Decisions
* **Columnar Storage:** Switched to a columnar database (like ClickHouse). Columnar databases only read the specific columns requested (e.g., `SUM(revenue)`), ignoring the rest of the row, which drastically reduces disk I/O and speeds up analytical queries by orders of magnitude.
* **Data Retention Policies:** Implemented tiered storage. Data < 30 days old lives on fast SSDs. Data > 30 days is rolled up and moved to cheaper, slower object storage (S3) and queried via federated engines (like Presto/Athena) when needed.

## Technology Choices
* **Message Broker:** Kafka.
* **Data Warehouse:** Snowflake, BigQuery, or ClickHouse.
* **ETL Tools:** Apache Airflow for orchestration, dbt for data transformation.
* **Visualization:** Custom React frontend or BI tools like Metabase/Superset.

## Common Interview Questions
* Why not just use read replicas of your main database for analytics?
* How do you handle late-arriving data in your aggregations?
* What is the difference between a row-oriented and a columnar database?

## Strong Answers
* "Read replicas are still row-oriented. If I want to sum the revenue column across 10 million rows, the database has to load the entire row into memory. A columnar database stores all the revenue values together on disk, allowing massive vectorized processing and compression."
* "Late-arriving data (e.g., offline mobile events syncing late) is handled by designing the ETL pipeline to be idempotent. We use 'watermarking' in stream processing. If late data arrives within the allowed window, we recalculate the aggregate. If it's too late, it's pushed to a dead-letter queue for manual intervention."

## Weak Answers
* "I'll just run a cron job to SELECT * from the production database every night." *(Will cause production outages and ignores real-time requirements).*
* "Just store everything in MongoDB." *(NoSQL is generally poor for complex analytical JOINs and aggregations).*

## Hiring Manager Notes
Analytics is about separating operational data (running the business) from analytical data (understanding the business). Strong candidates will immediately recognize the need for an OLAP system and discuss data modeling techniques like Star Schemas or Snowflake Schemas.

## Possible Follow-up Questions
* How do you ensure PII (Personally Identifiable Information) is stripped before data hits the data warehouse?
* How would you build a real-time alerting system on top of this event stream?

## System Design Discussion
Focus on the ETL (Extract, Transform, Load) process. Discuss how data gets from the operational databases into the analytical databases. Emphasize the importance of data quality, monitoring the pipelines for failures, and optimizing query performance using materialized views.
