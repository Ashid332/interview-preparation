# Document Databases (MongoDB)

## Overview
MongoDB is a leading NoSQL document database that stores data in flexible, JSON-like documents. It is highly scalable and allows for evolving schemas, making it ideal for rapid development and handling unstructured or semi-structured data.

## Interview Questions
**Question:** When would you choose MongoDB over a relational database like PostgreSQL?
- **Difficulty/Frequency/Companies:** Medium / High / Startups, Netflix, Uber
- **Excellent Answer:** MongoDB is preferred when the schema is highly dynamic or unknown in advance, when working with large volumes of semi-structured data (like JSON logs or product catalogs), or when you need horizontal scalability out-of-the-box (sharding). PostgreSQL is better for strict ACID requirements and complex, multi-table transactions.
- **Common Mistakes:** Saying MongoDB doesn't support transactions (it does, since v4.0), or suggesting it just because it's "faster" without context.

## Real-World Applications
- **Content Management Systems:** Storing articles, metadata, and user comments with varying structures.
- **IoT Data Logging:** Storing massive amounts of telemetry data where schemas frequently change.

## Practice Problems

| Problem Name | Type | Difficulty | Focus Area |
| --- | --- | --- | --- |
| Design a Product Catalog | System Design | Medium | Schema Design |
| Aggregation Pipeline Optimization | Query Optimization | Hard | MongoDB Aggregation |
| Sharding Strategy | Architecture | Hard | Horizontal Scaling |

## Hiring Manager Perspective
I want to see if the candidate understands document modeling. Do they know when to embed documents versus referencing them? Can they discuss the trade-offs of sharding keys?

## AI Interview Coach Prompts
- **ChatGPT:** "Quiz me on MongoDB aggregation pipelines. Provide a sample document structure and ask me to write a query to achieve a specific result."
- **Claude:** "Act as a system architect. Ask me to design a database schema for a complex e-commerce site using MongoDB, and challenge my embedding vs. referencing decisions."
- **Gemini:** "Provide a scenario where choosing MongoDB would be a terrible mistake, and ask me to explain why."
