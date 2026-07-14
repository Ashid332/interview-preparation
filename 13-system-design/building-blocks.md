# System Design Building Blocks

## Overview
Building blocks are the essential components used to construct large-scale systems. These include databases (SQL/NoSQL), caches (Redis, Memcached), message queues (Kafka, RabbitMQ), load balancers, and CDNs.

## Interview Questions

### Q1: When would you choose a Message Queue (like RabbitMQ) over an Event Streaming Platform (like Kafka)?
**Difficulty:** Medium | **Frequency:** High | **Companies:** Netflix, Uber, Stripe

**Excellent Answer:**
- **RabbitMQ (Message Queue):** Ideal for traditional task routing, point-to-point communication, and when you need complex routing logic or message acknowledgments (e.g., task processing workers). Messages are typically deleted after processing.
- **Kafka (Event Streaming):** Best for high-throughput, distributed event logging, and when multiple consumers need to read the same stream of events (e.g., analytics, real-time data pipelines). Data is persisted and can be replayed.

**Common Mistakes:**
- Treating Kafka as a simple task queue.
- Over-engineering a simple background job system by using Kafka instead of Redis/RabbitMQ.

## Real-World Applications
- **Caches:** Used by Netflix to store popular movie metadata at the edge.
- **Message Queues:** Used by Uber to asynchronously process ride receipts.
- **CDNs:** Used by Cloudflare to serve static assets globally with low latency.

## Practice Problems
| Problem | Difficulty | Focus Area | Link/Description |
|---|---|---|---|
| Design a Distributed Cache | Hard | Caching, Eviction | Implement an LRU cache service |
| Build a Task Scheduler | Medium | Message Queues, Workers | Schedule delayed tasks |

## Hiring Manager Perspective
Candidates often throw tools like Kafka or Redis at a problem because they are popular buzzwords. I look for the reasoning: do you know the operational complexity of running Kafka vs. a simpler Postgres queue for low-scale problems? Pragmatism is key.

## AI Interview Coach
**ChatGPT/Claude Prompt:**
```text
Act as a system architect. I will describe a scenario, and you will ask me to choose the appropriate building blocks (Databases, Caches, CDNs). Challenge my choices and ask me to justify the trade-offs of my selections.
```
