# 12-API Engineering and Design

## Overview
Application Programming Interfaces (APIs) are the contracts that allow different software systems to communicate. In modern software engineering, designing robust, scalable, and secure APIs is a fundamental skill. This section covers various API paradigms and best practices.

## Topics Covered
- [REST](rest.md)
- [GraphQL](graphql.md)
- [WebSockets](websockets.md)
- [gRPC](grpc.md)
- [API Design](api-design.md)

## Interview Questions

### Q1: How do you choose between REST, GraphQL, and gRPC?
**Difficulty:** Medium | **Frequency:** High | **Companies:** All
**Excellent Answer:**
REST is the standard for public-facing APIs due to its simplicity, cacheability, and widespread tooling. GraphQL is excellent for complex frontends that need to fetch nested data without over-fetching or under-fetching. gRPC is best for internal microservice-to-microservice communication where high performance, low latency, and strict contracts (Protobuf) are required.
**Common Mistakes:**
- Claiming one paradigm replaces the others completely.

## Real-World Applications
- Public third-party integrations (REST).
- Mobile application backends (GraphQL).
- Real-time trading dashboards (WebSockets).
- Internal service meshes (gRPC).

## Practice Problems

| Problem | Description | Difficulty |
|---------|-------------|------------|
| Paradigm Selection | Given a scenario (e.g., chat app, banking API), choose the best API paradigm and defend it. | Easy |
| API Gateway | Design an API Gateway architecture that routes to REST and gRPC backends. | Hard |

## Hiring Manager Perspective
"I look for engineers who understand that an API is a product. You should care deeply about developer experience, backwards compatibility, and choosing the right tool for the specific communication need."

## AI Interview Coach
**Prompt:**
> "Act as a Staff Engineer interviewing me. Ask me to compare and contrast REST, GraphQL, and gRPC for different use cases. Push back on my choices to test my understanding."
