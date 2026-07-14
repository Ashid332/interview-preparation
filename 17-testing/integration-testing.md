# Integration Testing

## Overview
Integration testing is the phase where individual software modules are combined and tested as a group. The purpose is to expose faults in the interaction between integrated units. Unlike unit tests, integration tests often involve external components like databases, APIs, message queues, and file systems. They ensure that the different parts of the system communicate correctly.

## Interview Questions

### Question 1: How do you handle testing database interactions in integration tests?
* **Difficulty:** Medium
* **Frequency:** High
* **Companies:** Amazon, Stripe, Square

**Excellent Answer:**
For database integration tests, it's crucial to test against a real database instance rather than mocking the database driver, as the goal is to verify the SQL queries and schema. Best practices include using ephemeral databases (like Testcontainers or an in-memory database like SQLite, though Testcontainers with the actual DB engine is preferred to avoid dialect mismatches). Each test or test suite should run in a clean state, which can be achieved by applying database migrations before the suite, and wrapping each test in a transaction that is rolled back at the end, or by truncating tables between tests.

**Common Mistakes:**
* Suggesting mocking the database (which defeats the purpose of an integration test).
* Not isolating tests, leading to flaky tests due to shared state (e.g., Test A inserts data that causes Test B to fail).

### Question 2: What is contract testing, and when would you use it?
* **Difficulty:** Hard
* **Frequency:** Medium
* **Companies:** Netflix, Uber, Atlassian

**Excellent Answer:**
Contract testing is a methodology used in microservices architectures to ensure that two separate systems (like an API provider and an API consumer) are compatible and can communicate. Instead of testing the two systems together in a live environment, contract tests verify that the consumer's expectations (the "contract") are met by the provider's responses. Tools like Pact are often used. It's used to prevent breaking changes in APIs without needing to spin up the entire microservice ecosystem for end-to-end testing, making the CI pipeline faster and more reliable.

**Common Mistakes:**
* Confusing contract testing with standard end-to-end API testing.
* Not understanding the difference between consumer-driven and provider-driven contracts.

## Real-World Applications
* **Microservices Communication:** Ensuring that a checkout service correctly sends messages to an inventory service via Kafka.
* **Third-Party Integrations:** Testing the integration with a payment gateway like Stripe in a sandbox environment to ensure webhook handling is correct.

## Practice Problems

| Problem | Type | Focus | Difficulty |
| :--- | :--- | :--- | :--- |
| Set up Testcontainers for a PostgreSQL DB | Practical | Test environments | Medium |
| Implement a consumer-driven contract test | System Design | Microservices, API contracts | Hard |

## Hiring Manager Perspective
When discussing integration testing, managers look for awareness of test flakiness and environment management. They want engineers who know how to set up reproducible test environments (e.g., Docker, Testcontainers) and who understand the trade-offs between mocking an API vs. hitting a test instance of that API.

## AI Interview Coach
**Prompt for ChatGPT/Claude/Gemini:**
> "Simulate a technical interview focused on integration testing in a microservices environment. Ask me how I would design integration tests for a service that relies on 3 other internal APIs and a relational database. Challenge my approach on performance and reliability."
