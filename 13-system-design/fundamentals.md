# System Design Fundamentals

## Overview
System design fundamentals form the theoretical foundation of distributed systems. Key concepts include the CAP theorem, scalability (horizontal vs. vertical), redundancy, latency vs. throughput, and consistency models.

## Interview Questions

### Q1: Explain the CAP Theorem and how it applies to database selection.
**Difficulty:** Medium | **Frequency:** Very High | **Companies:** Google, Meta, Amazon

**Excellent Answer:**
The CAP theorem states that a distributed data store can guarantee only two of the following three: Consistency, Availability, and Partition Tolerance.
Since network partitions (P) are unavoidable in distributed systems, we must choose between Consistency (C) and Availability (A).
- **CP Systems:** Return an error if data cannot be guaranteed consistent (e.g., MongoDB, HBase). Good for financial systems.
- **AP Systems:** Return the most recent available data, even if stale (e.g., Cassandra, DynamoDB). Good for social media feeds where uptime is critical.

**Common Mistakes:**
- Claiming a system can be strictly "CA" across a wide-area network.
- Not understanding the difference between strong and eventual consistency.

## Real-World Applications
- **Amazon DynamoDB:** Prioritizes high availability and partition tolerance (AP) for shopping cart data.
- **Banking Systems:** Use relational databases prioritizing consistency (CP) to prevent double-spending.

## Practice Problems
| Problem | Difficulty | Focus Area | Link/Description |
|---|---|---|---|
| Evaluate PACELC Theorem | Medium | Advanced Distributed Systems | Discuss extension of CAP |
| Sharding Strategy | Medium | Database Scaling | Design sharding for a global user base |

## Hiring Manager Perspective
A solid grasp of fundamentals shows you understand *why* things work, not just *how*. I want to see if you can balance theoretical rules with practical business needs—sometimes eventual consistency is perfectly fine for the product!

## AI Interview Coach
**ChatGPT/Claude Prompt:**
```text
Act as an engineering mentor. Quiz me on system design fundamentals, specifically focusing on consistency models, replication strategies, and the CAP theorem. Ask one question at a time and grade my responses.
```
