# Database Comparison & Selection

## Overview
Choosing the right database involves analyzing access patterns, scalability needs, consistency requirements (CAP theorem), and data structure. This topic compares RDBMS, Key-Value, Document, Columnar, and Graph databases.

## Interview Questions
**Question:** Explain the CAP theorem and how it applies to choosing between Cassandra and PostgreSQL.
- **Difficulty/Frequency/Companies:** Hard / High / Amazon, Netflix, Apple
- **Excellent Answer:** CAP theorem states a distributed system can only guarantee two of three: Consistency, Availability, and Partition Tolerance. In a network partition (P), you must choose between C and A. PostgreSQL traditionally prioritizes Consistency (CP), failing requests if sync fails. Cassandra prioritizes Availability (AP), remaining available for reads/writes but allowing eventual consistency.
- **Common Mistakes:** Stating you can have all three in normal operations without explaining what happens during a partition, or misunderstanding "Consistency" in CAP (it's linearizability, not ACID consistency).

## Real-World Applications
- **Polyglot Persistence:** An e-commerce site using PostgreSQL for orders (ACID), Redis for cart/sessions (Speed), and ElasticSearch for product search.
- **Graph Databases (Neo4j):** Recommendation engines and fraud detection based on relationships.

## Practice Problems

| Problem Name | Type | Difficulty | Focus Area |
| --- | --- | --- | --- |
| Choose the DB for a Chat App | System Design | Medium | Trade-offs |
| CAP Theorem Scenarios | Concept | Medium | Distributed Systems |
| Evaluate NewSQL (CockroachDB) | Architecture | Hard | Distributed SQL |

## Hiring Manager Perspective
The best candidates show pragmatism. There is no "perfect" database. I want to hear "It depends" followed by a detailed analysis of read/write ratios, latency requirements, and operational complexity.

## AI Interview Coach Prompts
- **ChatGPT:** "Present 3 different application architectures and ask me to choose the best database for each, justifying my choice."
- **Claude:** "Act as an interviewer grilling me on the CAP theorem and PACELC theorem. Ask me how popular databases fit into these models."
- **Gemini:** "Challenge me to defend a poor database choice for a specific scenario, forcing me to argue the trade-offs."
