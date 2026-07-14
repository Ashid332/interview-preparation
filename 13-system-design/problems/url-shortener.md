# System Design Problem: URL Shortener

## Overview
Designing a URL shortener (like TinyURL or Bitly) is a classic system design interview question. It focuses on hashing, database scaling, read-heavy workloads, and distributed unique ID generation.

## Interview Questions

### Q1: Design a URL Shortener. How do you generate the short URL?
**Difficulty:** Medium | **Frequency:** Very High | **Companies:** Meta, Amazon, Microsoft

**Excellent Answer:**
The core challenge is generating a unique short key for a long URL.
1. **Approach 1: Base62 Encoding of an Auto-Incrementing ID:**
   Use a distributed ID generator (like Twitter Snowflake or a standalone database with a counter) to get a unique integer. Convert this integer to Base62 (A-Z, a-z, 0-9). This guarantees uniqueness and prevents collisions.
2. **Approach 2: MD5/SHA-1 Hashing:**
   Hash the long URL, take the first 7 characters, and resolve collisions using a database check. (Less efficient due to collision resolution).
Base62 of a unique ID is generally preferred for its determinism and simplicity.

**Common Mistakes:**
- Forgetting to handle high availability for the ID generator.
- Not discussing caching (e.g., Redis) to handle the read-heavy nature of redirection (99% reads, 1% writes).
- Ignoring how to handle URL expiration or malicious URLs.

## Real-World Applications
- **Bitly / TinyURL:** Link shortening for Twitter or SMS messages where character count is limited.
- **Internal Tools:** Shortening long dashboard or query URLs for easier sharing.

## Practice Problems
| Problem | Difficulty | Focus Area | Link/Description |
|---|---|---|---|
| Custom Aliases | Medium | Database Schema | Add support for user-defined custom short links |
| Analytics Dashboard | Hard | Stream Processing | Track click metrics in real-time |

## Hiring Manager Perspective
This is a baseline question to see if a candidate can handle a read-heavy system. I want to see them quickly identify the bottleneck (database reads) and propose caching. Strong candidates will proactively bring up the problem of distributed ID generation without being prompted.

## AI Interview Coach
**ChatGPT/Claude Prompt:**
```text
Act as an interviewer. Ask me to design a URL shortener. Go through requirements gathering, capacity estimation, API design, database schema, and high-level architecture. Critically evaluate my method for handling high read volume.
```
