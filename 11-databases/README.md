# Databases Overview

## Overview
Databases are the core of any application, responsible for storing, retrieving, and managing data efficiently. Understanding different types of databases, their internal workings, and design trade-offs is crucial for engineering interviews, especially for backend and full-stack roles.

## Interview Questions
**Question:** What are the ACID properties in a database?
- **Difficulty/Frequency/Companies:** Medium / High / Google, Meta, Amazon
- **Excellent Answer:** ACID stands for Atomicity (all-or-nothing transactions), Consistency (data remains valid according to rules), Isolation (concurrent transactions don't interfere), and Durability (committed transactions survive crashes). You should provide a practical example like a bank transfer to illustrate these.
- **Common Mistakes:** Confusing isolation with consistency or failing to explain how durability is achieved (e.g., via write-ahead logging).

## Real-World Applications
- **E-commerce:** Managing inventory and processing transactions where ACID properties are mandatory.
- **Social Media:** Storing graph relationships and activity feeds using scalable, distributed databases.

## Practice Problems

| Problem Name | Type | Difficulty | Focus Area |
| --- | --- | --- | --- |
| Implement a Key-Value Store | System Design | Hard | Storage, Concurrency |
| Design a Distributed Cache | System Design | Hard | Caching, Eviction |
| SQL vs NoSQL Selection | Behavioral/Architecture | Medium | Trade-offs |

## Hiring Manager Perspective
I look for candidates who don't just know SQL syntax but understand when to use a relational vs. non-relational database. Can they discuss index types, normalization vs. denormalization, and scaling strategies?

## AI Interview Coach Prompts
- **ChatGPT:** "Act as a senior engineering manager. Ask me a system design question focusing on choosing the right database for a high-throughput messaging app. Critique my answer."
- **Claude:** "Give me 5 intermediate database interview questions and score my answers out of 10 based on depth of technical knowledge."
- **Gemini:** "Simulate a technical interview focusing on database scaling techniques. Ask one question at a time."
