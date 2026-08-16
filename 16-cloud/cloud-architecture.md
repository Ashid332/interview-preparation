# Cloud Architecture

## Overview
Cloud Architecture refers to how individual technologies are integrated to create environments that are scalable, reliable, secure, and cost-effective. It involves high-level system design principles and applying best practices (like the Well-Architected Framework) regardless of the specific cloud provider.

## Interview Questions

### Question 1: What are the differences between Monolithic, Microservices, and Serverless architectures?
* **Difficulty:** Medium
* **Frequency:** Very High
* **Companies:** Uber, Airbnb, Stripe

**Excellent Answer:**
- **Monolith:** All components (UI, business logic, data access) are bundled into a single codebase and deployed as a single unit. It's easy to start but hard to scale and maintain as the team grows.
- **Microservices:** The application is broken down into small, independent services communicating over APIs. This allows independent scaling and deployments but introduces network complexity and distributed data challenges.
- **Serverless:** The cloud provider dynamically manages the allocation of machine resources. The developer writes functions (like AWS Lambda) that scale to zero when unused and scale infinitely under load, shifting the operational burden entirely to the provider, but potentially introducing vendor lock-in and cold starts.

**Common Mistakes:**
- Claiming microservices are inherently "better" without acknowledging the significant operational complexity they introduce.
- Ignoring the cold-start latency issues associated with serverless environments.

## Real-World Applications
Designing highly available (HA) systems using multi-region deployments, implementing event-driven architectures for asynchronous processing, and establishing robust disaster recovery strategies.

## Practice Problems
| Problem | Description | Complexity | Link |
| --- | --- | --- | --- |

## Hiring Manager Perspective
System Design and Architecture interviews are meant to test your ability to make trade-offs. Managers want to see you weigh the pros and cons of SQL vs NoSQL, synchronous vs asynchronous communication, and consistency vs availability (CAP theorem) in the context of the cloud.

## AI Interview Coach
**ChatGPT/Claude/Gemini Prompt:**
> "Act as a Principal Engineer doing a System Design interview. Ask me to design a URL shortening service (like Bitly) deployed on the cloud. Probe me on my database choices, caching strategy, and how the system will handle 10,000 requests per second."
