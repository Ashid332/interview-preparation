# In-Memory Data Stores (Redis)

## Overview
Redis is an open-source, in-memory key-value data store used as a database, cache, message broker, and queue. Because data resides in memory, read and write operations are extremely fast.

## Interview Questions
**Question:** Explain how Redis handles data persistence if it's an in-memory store.
- **Difficulty/Frequency/Companies:** Medium / High / Twitter, Discord, Amazon
- **Excellent Answer:** Redis offers two main persistence options: RDB (Redis Database Backup) which takes point-in-time snapshots, and AOF (Append Only File) which logs every write operation. You can use them together for optimal safety and performance.
- **Common Mistakes:** Assuming Redis is strictly ephemeral and loses all data on restart, or failing to mention the latency trade-offs of AOF fsync policies.

## Real-World Applications
- **Session Management:** Storing user session tokens for fast verification.
- **Leaderboards:** Using Redis Sorted Sets to maintain real-time ranking systems.
- **Caching:** Acting as a look-aside cache to reduce load on the primary database.

## Practice Problems

| Problem Name | Type | Difficulty | Focus Area |
| --- | --- | --- | --- |
| Design a Rate Limiter | System Design | Medium | Redis commands, Concurrency |
| Real-time Leaderboard | Architecture | Easy | Sorted Sets |
| Cache Stampede Prevention | Concept | Hard | Concurrency, Caching |

## Hiring Manager Perspective
A strong candidate knows Redis is more than just string keys. I look for familiarity with data structures like Hashes, Lists, Sets, and Sorted Sets, and knowledge of caching patterns (Cache Aside, Write-Through).

## AI Interview Coach Prompts
- **ChatGPT:** "Test my knowledge on Redis data structures. Give me use cases and ask which Redis type fits best."
- **Claude:** "Simulate an interview question where I need to design a distributed rate limiter using Redis. Evaluate my approach to race conditions."
- **Gemini:** "Ask me about cache eviction policies in Redis (like LRU and LFU) and when to use each."
