# System Design Quick Reference

## 1. The 5-Step Process (PEDALS)
1.  **Process Requirements:** Functional (What it does) & Non-Functional (Scale, latency, availability).
2.  **Estimate:** Traffic (QPS), Storage (per day/year), Bandwidth. (Rule of thumb: 1M DAU = ~10 QPS).
3.  **Design High-Level:** Draw the happy path (Client -> LB -> App Servers -> DB).
4.  **Architecture Deep Dive:** Address bottlenecks (Caching, Sharding, Async Queues).
5.  **List Trade-offs:** Justify choices (e.g., CP vs AP, SQL vs NoSQL).

## 2. CAP Theorem
*   **Consistency (C):** Every read receives the most recent write.
*   **Availability (A):** Every request receives a non-error response (but maybe not the latest data).
*   **Partition Tolerance (P):** System continues to operate despite network drops.
*   *Rule:* You can only pick 2 over a network. Usually choosing between CP (Bank) and AP (Social Media).

## 3. Database Selection
*   **Relational (SQL - Postgres, MySQL):** ACID compliant, structured data, complex joins. (Default choice).
*   **Document (NoSQL - MongoDB, DynamoDB):** Flexible schema, rapid iteration, massive scale horizontally.
*   **Key-Value (Redis, Memcached):** Ultra-fast reads/writes, caching, session management.
*   **Wide-Column (Cassandra):** Time-series data, high write throughput, decentralized.
*   **Graph (Neo4j):** Complex relationships, recommendation engines, social networks.

## 4. Scaling Strategies
*   **Compute:** Vertical (bigger machine), Horizontal (more machines + Load Balancer).
*   **Database:** Read Replicas (scale reads), Sharding (scale writes/storage), Partitioning.
*   **Performance:** Caching (CDN for static, Redis for dynamic), Asynchronous processing (Message Queues like Kafka/RabbitMQ for heavy background tasks).
