# GraphQL Interview Guide

## Overview
GraphQL is a query language for APIs and a runtime for fulfilling those queries with your existing data. Developed by Facebook, it provides a complete and understandable description of the data in your API, giving clients the power to ask for exactly what they need and nothing more.

## Interview Questions

### Q1: How does GraphQL solve the over-fetching and under-fetching problems of REST?
**Difficulty:** Easy | **Frequency:** High | **Companies:** Meta, Shopify, Airbnb
**Excellent Answer:**
In REST, an endpoint returns a fixed data structure. Over-fetching happens when a client downloads more data than it needs (e.g., fetching a full User object just to get the username). Under-fetching happens when a specific endpoint doesn't provide enough data, forcing the client to make additional requests (N+1 problem). GraphQL solves this by allowing the client to specify the exact shape and fields of the data it requires in a single query.
**Common Mistakes:**
- Failing to mention that GraphQL can introduce severe backend performance issues if not carefully managed.

### Q2: What is the N+1 problem in GraphQL and how do you solve it?
**Difficulty:** Hard | **Frequency:** Very High | **Companies:** Meta, GitHub
**Excellent Answer:**
The N+1 problem occurs when a query fetches a list of N items, and the GraphQL resolver makes a separate database query to fetch a related field for each item (1 initial query + N sub-queries). The standard solution is to use a DataLoader, which batches and caches requests to the database, combining the N queries into a single query using an `IN` clause.

## Real-World Applications
- Complex Single Page Applications (SPAs).
- Mobile apps where bandwidth is a constraint.
- Aggregation layers over multiple microservices.

## Practice Problems

| Problem | Description | Difficulty |
|---------|-------------|------------|
| Schema Design | Design a GraphQL schema for a library (Authors and Books). | Medium |
| Resolvers | Write a resolver that implements DataLoader to fix an N+1 issue. | Hard |

## Hiring Manager Perspective
"GraphQL is great for clients but hard for servers. I'm looking for candidates who understand the security and performance implications of GraphQL, such as query complexity analysis and the N+1 problem."

## AI Interview Coach
**Prompt:**
> "Act as a backend interviewer. Ask me about the pros and cons of GraphQL vs REST, and dive deep into how to optimize GraphQL resolvers using DataLoaders."
