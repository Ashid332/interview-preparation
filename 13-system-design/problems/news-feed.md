# System Design Problem: News Feed

## Overview
Designing a news feed (like Twitter, Instagram, or Facebook) requires handling massive read throughput, assembling personalized timelines from multiple sources, and addressing the "celebrity problem" (fan-out on write vs. fan-out on read).

## Interview Questions

### Q1: Explain the difference between Fan-out on Write (Push) and Fan-out on Read (Pull). When would you use each?
**Difficulty:** Hard | **Frequency:** High | **Companies:** Twitter, Meta, LinkedIn

**Excellent Answer:**
- **Fan-out on Write (Push):** When a user publishes a post, the system immediately pushes the post ID into the pre-computed timeline caches of all their followers. Best for fast reads (O(1) fetch), but suffers when a user has millions of followers (the "Justin Bieber problem"), leading to huge write delays.
- **Fan-out on Read (Pull):** The timeline is generated dynamically when the user requests it by querying all the users they follow and merging their recent posts. Best for celebrities, as it avoids massive write operations, but slows down the feed generation (reads).
- **Hybrid Approach:** Use Push for standard users and Pull for celebrities. When fetching a feed, the system pulls from the user's pre-computed inbox (Push) and merges it at runtime with recent posts from celebrities they follow (Pull).

**Common Mistakes:**
- Suggesting a pure SQL JOIN query to generate feeds at runtime for billions of users.
- Failing to address the celebrity fan-out bottleneck.

## Real-World Applications
- **Social Media:** Twitter timelines, Instagram feeds, TikTok algorithms.
- **Activity Streams:** GitHub dashboard, internal company update feeds.

## Practice Problems
| Problem | Difficulty | Focus Area | Link/Description |
|---|---|---|---|
| Feed Ranking | Hard | Machine Learning | Integrate a ranking ML model into feed generation |
| Infinite Scroll | Medium | Pagination | Implement cursor-based pagination for feed consumption |

## Hiring Manager Perspective
I look for the candidate's understanding of asynchronous processing. Can they identify that feed generation shouldn't block the post creation API? The hybrid fan-out model is the standard answer; candidates who can articulate *how* to determine who is a celebrity dynamically score extra points.

## AI Interview Coach
**ChatGPT/Claude Prompt:**
```text
Act as a Staff Engineer interviewing me. Ask me to design the Twitter timeline architecture. Focus intensely on how I manage data replication and caching strategies to ensure sub-200ms load times for the feed.
```
