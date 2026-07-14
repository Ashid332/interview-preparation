# System Design Interview Guide

## Overview
System design interviews assess your ability to design complex, scalable, and highly available systems. This section covers fundamental concepts, building blocks, and common practice problems to help you architect robust solutions and communicate tradeoffs effectively.

## Interview Questions

### Q1: How do you approach a system design interview?
**Difficulty:** Medium | **Frequency:** High | **Companies:** FAANG, Uber, Airbnb

**Excellent Answer:**
A structured approach is essential:
1. **Clarify Requirements:** Understand functional and non-functional requirements (e.g., scale, latency, availability).
2. **Back-of-the-envelope Estimation:** Calculate storage, bandwidth, and compute needs.
3. **High-Level Design:** Draw the core components and data flow.
4. **Deep Dive:** Address specific bottlenecks, database schemas, and component scaling.
5. **Trade-offs:** Discuss choices like SQL vs. NoSQL, consistency vs. availability.

**Common Mistakes:**
- Diving into details too early without defining high-level architecture.
- Ignoring non-functional requirements.
- Not discussing tradeoffs of the proposed design.

## Real-World Applications
System design principles are used daily to build everything from scalable e-commerce backends to low-latency real-time chat platforms and reliable cloud infrastructure.

## Practice Problems
| Problem | Difficulty | Focus Area | Link/Description |
|---|---|---|---|
| Design a URL Shortener | Medium | Databases, Hashing | `problems/url-shortener.md` |
| Design a Chat System | Hard | WebSockets, Real-time | `problems/chat-system.md` |
| Design a News Feed | Hard | Fan-out, Caching | `problems/news-feed.md` |

## Hiring Manager Perspective
I look for candidates who can take ambiguous requirements and structure them into a concrete technical plan. The best candidates drive the conversation, proactively point out bottlenecks, and justify their technology choices without getting overly defensive when challenged.

## AI Interview Coach
**ChatGPT/Claude Prompt:**
```text
Act as a senior engineering interviewer. Conduct a 30-minute system design interview with me. Start by asking me to design a basic distributed system of your choice. Evaluate my ability to gather requirements, propose a high-level design, and discuss tradeoffs. Provide feedback after we conclude.
```
