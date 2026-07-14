# Integration Patterns

## Overview
Integration patterns define how different parts of a system communicate with each other and with external services. This covers RESTful APIs, GraphQL, gRPC, message queues (RabbitMQ, Kafka), and event-driven architectures.

## Interview Questions
* **Difficulty:** Medium to Hard
* **Frequency:** High
* **Companies:** Enterprise companies, fintech, SaaS providers.

### Excellent Answer
"For the payment processing service, synchronous REST calls were too fragile; if the external provider went down, our service blocked. We switched to an event-driven pattern using Kafka. Now, we publish a 'PaymentRequested' event, return a 202 Accepted to the client, and process the payment asynchronously."

### Common Mistakes
* Not understanding idempotency when designing webhooks or retries.
* Using synchronous communication where asynchronous messaging would be more resilient.
* Failing to handle API rate limits from third-party integrations.

## Real-World Applications
* Integrating third-party authentication (OAuth2) or payment gateways (Stripe).
* Building data pipelines that ingest logs from various microservices.
* Designing mobile app APIs with GraphQL to prevent over-fetching of data.

## Practice Problems

| Problem | Topic | Difficulty | Focus |
| :--- | :--- | :--- | :--- |
| Design Webhook System | Integration | Hard | Idempotency/Retries |
| REST vs GraphQL | API Design | Medium | Trade-offs |
| Message Queue Design | Async | Hard | Kafka/RabbitMQ |

## Hiring Manager Perspective
"Modern software is rarely standalone. I need engineers who know how to safely integrate with brittle external systems, handle network failures gracefully, and design APIs that other developers actually want to use."

## AI Interview Coach

**Prompt for ChatGPT/Claude/Gemini:**
> "I need to design a system that integrates with a slow, unreliable third-party API. Ask me how I would handle rate limiting, timeouts, retries, and data consistency. Evaluate my proposed integration patterns."
