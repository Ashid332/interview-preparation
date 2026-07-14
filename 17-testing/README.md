# Software Testing

## Overview
Software testing is a critical phase in the software development lifecycle that ensures the application meets its requirements and is free of defects. It encompasses various methodologies, from checking individual components to verifying the entire system's behavior. In engineering interviews, demonstrating a strong grasp of testing principles shows that you care about code quality, maintainability, and user experience.

## Interview Questions

### Question 1: What is the Test Pyramid and why is it important?
* **Difficulty:** Medium
* **Frequency:** High
* **Companies:** Meta, Google, Amazon

**Excellent Answer:**
The Test Pyramid is a metaphor that groups software tests into buckets of different granularity. It suggests that you should have a large number of small, fast unit tests at the base, fewer medium-sized integration tests in the middle, and a very small number of slow, brittle end-to-end (E2E) tests at the top. This structure is important because it optimizes the feedback loop: unit tests are fast to run and pinpoint errors exactly, while E2E tests are slow and complex to maintain. By pushing tests down the pyramid, teams can achieve high confidence in their code while maintaining fast build times and low maintenance overhead.

**Common Mistakes:**
* Recommending writing mostly E2E tests because they "test the real thing."
* Failing to mention the cost (time and maintenance) of different test types.

## Real-World Applications
* **Continuous Integration/Continuous Deployment (CI/CD):** Automated test suites are the backbone of CI/CD pipelines, acting as quality gates before code is deployed to production.
* **Refactoring:** A robust test suite allows developers to confidently refactor code without fear of breaking existing functionality.

## Practice Problems

| Problem | Type | Focus | Difficulty |
| :--- | :--- | :--- | :--- |
| Implement a test suite for a shopping cart | Practical | Test coverage, edge cases | Medium |
| Design a testing strategy for a microservices app | System Design | Integration, mocks, E2E | Hard |

## Hiring Manager Perspective
Hiring managers look for engineers who view testing not as an afterthought or a chore, but as an integral part of the development process. They want to see a pragmatic approach to testing—understanding the trade-offs between different types of tests and knowing when to apply them. "100% code coverage" is less important than meaningful tests that catch regressions.

## AI Interview Coach
**Prompt for ChatGPT/Claude/Gemini:**
> "Act as a Senior Engineering Manager conducting an interview. Ask me 3 progressive questions about software testing principles and the test pyramid. Evaluate my responses based on clarity, pragmatism, and understanding of CI/CD integration, then provide feedback."
