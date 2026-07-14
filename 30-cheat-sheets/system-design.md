# System Design Cheat Sheet

## Key Concepts
| Concept | Description |
|---|---|
| Scalability | Ability of a system to handle increased load (vertical vs. horizontal scaling). |
| Consistency vs. Availability | CAP Theorem: In presence of a network partition, choose Consistency or Availability. |
| Load Balancing | Distributing incoming network traffic across multiple servers. |
| Caching | Storing frequently accessed data in memory (Redis, Memcached) to reduce database load. |
| Sharding | Horizontally partitioning a database into smaller, faster, more easily managed parts. |

## Must-Know Items
- The 4-step framework: 1. Understand requirements 2. Propose high-level design 3. Deep dive into core components 4. Identify bottlenecks.
- Back-of-the-envelope estimations (QPS, storage, bandwidth).
- Differences between SQL and NoSQL databases.
- Microservices vs. Monolith architectures.

## Common Interview Questions (Quick)
1. Design a URL shortener (TinyURL).
2. Design a messaging app (WhatsApp).
3. Design a social media feed (Twitter/X).
4. Design a rate limiter.
5. Design an e-commerce checkout system.

## Critical Commands/Patterns
*Standard Component Patterns:*
- Client -> Load Balancer -> Web Servers -> Application Servers -> Database
- Cache aside: App checks cache, if miss, checks DB, writes to cache.
- Message Queue: Decouple producers and consumers (Kafka, RabbitMQ) for asynchronous processing.

## Decision Framework
- **SQL vs. NoSQL:** Need ACID, structured data, complex joins? SQL. Need high write throughput, flexible schema, easy horizontal scaling? NoSQL.
- **Polling vs. WebSockets:** Infrequent updates? Polling/Long-polling. Real-time, bidirectional? WebSockets.

## Common Mistakes
- Jumping into the solution without gathering functional and non-functional requirements.
- Over-engineering the initial solution (start simple, then scale).
- Ignoring single points of failure.
- Forgetting to mention monitoring, logging, and alerting.

## One-Minute Review
- Clarify requirements -> Establish APIs/Data Models -> High-level architecture -> Scale and refine (Load balancers, Caches, Sharding, Queues) -> Discuss trade-offs.
