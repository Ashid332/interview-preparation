# System Design Problem: Rate Limiter

## Overview
A rate limiter controls the rate of traffic sent by a client or a service. It protects backend systems from DDoS attacks, brute force attacks, and accidental traffic spikes, ensuring fair usage and high availability.

## Interview Questions

### Q1: What are the common algorithms used for rate limiting, and which would you choose for a distributed API gateway?
**Difficulty:** Medium | **Frequency:** High | **Companies:** Stripe, Cloudflare, Amazon

**Excellent Answer:**
Common algorithms include:
1. **Token Bucket:** Tokens are added at a fixed rate. Requests consume tokens. Good for allowing short bursts of traffic.
2. **Leaky Bucket:** Requests enter a queue and are processed at a fixed rate. Smooths out traffic.
3. **Fixed Window Counter:** Counts requests per time window (e.g., 00:00 - 00:01). Can allow double traffic at window boundaries.
4. **Sliding Window Log:** Stores timestamp of each request. Perfectly accurate but memory-intensive.
5. **Sliding Window Counter:** Hybrid of fixed and sliding log, using weighted counts.

For a distributed API gateway, **Token Bucket** backed by Redis is often best. To handle distributed synchronization, use Redis with Lua scripts (to ensure atomicity of check-and-decrement operations) or use an eventual consistency model if strict limits aren't strictly required.

**Common Mistakes:**
- Forgetting race conditions when multiple API servers check/update the counter simultaneously.
- Storing the counter in a relational database instead of an in-memory cache like Redis.
- Blocking legitimate traffic due to poorly sized buckets.

## Real-World Applications
- **Public APIs:** Stripe or GitHub limiting requests to 1000/hour per API key.
- **Login Systems:** Preventing password brute-forcing.
- **Cloud Infrastructure:** AWS limiting API calls to prevent resource exhaustion.

## Practice Problems
| Problem | Difficulty | Focus Area | Link/Description |
|---|---|---|---|
| Distributed Rate Limiter | Hard | Concurrency, Redis | Implement a sliding window counter across 50 nodes |
| Tiered Rate Limiting | Medium | API Design | Support different limits for Free vs Premium users |

## Hiring Manager Perspective
Rate limiting is a great test of concurrency knowledge. I want candidates to recognize the race conditions when reading and writing counters from a cache, and I want to hear them discuss atomic operations (like Redis INCR or Lua scripts).

## AI Interview Coach
**ChatGPT/Claude Prompt:**
```text
Act as a backend systems interviewer. Ask me to design a distributed rate limiter for a public-facing API. Challenge me on the pros and cons of Token Bucket vs. Sliding Window algorithms.
```
