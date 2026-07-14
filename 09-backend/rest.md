# REST API Interview Guide

## Overview
Representational State Transfer (REST) is an architectural style for designing networked applications. It relies on a stateless, client-server, cacheable communications protocol — almost always HTTP. REST is the standard for building web APIs.

## Interview Questions

### Q1: What makes an API truly "RESTful"?
**Difficulty:** Medium | **Frequency:** High | **Companies:** Stripe, Twilio, GitHub
**Excellent Answer:**
A truly RESTful API adheres to six constraints: Client-Server architecture, Statelessness (no client context stored on the server between requests), Cacheability, a Uniform Interface (resource identification, standard HTTP methods), Layered System, and (optionally) Code on Demand. It uses standard HTTP verbs (GET, POST, PUT, PATCH, DELETE) properly and relies on URIs to identify resources.
**Common Mistakes:**
- Confusing any HTTP JSON API with a REST API.
- Forgetting to mention statelessness as a core constraint.

### Q2: What is idempotency and why is it important in REST?
**Difficulty:** Medium | **Frequency:** High | **Companies:** Square, PayPal
**Excellent Answer:**
An idempotent operation produces the same result no matter how many times it is executed. In REST, GET, PUT, and DELETE should be idempotent. POST is not. This is crucial for distributed systems and unreliable networks—if a client times out waiting for a response to a DELETE request, it can safely retry the request without worrying about side effects.

## Real-World Applications
- Public Developer APIs (e.g., Stripe, Twitter).
- Standard web application backends.
- CRUD applications.

## Practice Problems

| Problem | Description | Difficulty |
|---------|-------------|------------|
| URI Design | Design the URIs for a blogging platform (Users, Posts, Comments). | Easy |
| Status Codes | Given 5 error scenarios, select the most appropriate HTTP status code. | Medium |

## Hiring Manager Perspective
"REST is ubiquitous. I want to see that you respect HTTP semantics. Don't use POST for everything. Use proper status codes (400 vs 401 vs 403 vs 404). Understand how to design clean resource URLs."

## AI Interview Coach
**Prompt:**
> "Act as an API designer interviewing me. Ask me about HTTP methods, idempotency, and proper status code usage. Give me a scenario and ask me to design the REST endpoints for it."
