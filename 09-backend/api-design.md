# API Design Interview Guide

## Overview
API Design is the process of developing application programming interfaces that expose data and application functionality for use by developers and users. Good API design focuses on developer experience, consistency, security, and scalability.

## Interview Questions

### Q1: How do you handle API versioning?
**Difficulty:** Medium | **Frequency:** High | **Companies:** Stripe, GitHub, Atlassian
**Excellent Answer:**
There are several ways to version APIs. The most common are:
1. **URI Versioning:** `/api/v1/users`. Simple, but violates the REST principle that a URI represents a resource, not a version.
2. **Header Versioning:** Sending `Accept-Version: v1` or a custom header. Cleaner URLs, but harder to test in a browser.
3. **Query Parameter:** `/api/users?version=1`.
Regardless of the method, the most important thing is to maintain backwards compatibility for as long as possible and have a clear deprecation policy.
**Common Mistakes:**
- Suggesting breaking changes without a deprecation phase.

### Q2: How do you implement pagination in an API?
**Difficulty:** Medium | **Frequency:** High | **Companies:** Twitter, Meta
**Excellent Answer:**
1. **Offset-based:** `?limit=20&offset=40`. Easy to implement, but suffers from performance issues on large datasets and data drift (if items are added/deleted while paginating, items might be skipped or duplicated).
2. **Cursor-based:** `?cursor=xyz123&limit=20`. The cursor is a pointer to a specific row. It scales perfectly and handles data drift, making it the industry standard for infinite scroll and high-frequency APIs.

## Real-World Applications
- Designing Stripe's billing API.
- Designing Twitter's public timeline API.

## Practice Problems

| Problem | Description | Difficulty |
|---------|-------------|------------|
| Rate Limiting | Design the HTTP headers and response codes for an API rate limiter. | Medium |
| Webhooks | Design an architecture to reliably deliver webhooks to third-party integrations. | Hard |

## Hiring Manager Perspective
"API design is about empathy for the developers consuming your service. I look for consistency in naming conventions, proper error handling (standardized error payloads), and smart decisions around pagination and versioning."

## AI Interview Coach
**Prompt:**
> "Act as an API Design Interviewer. Ask me to design a public API for a ride-sharing service like Uber. Focus on resource naming, pagination, versioning, and rate limiting."
