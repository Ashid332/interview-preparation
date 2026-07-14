# Testing Strategy

## Overview
A comprehensive testing strategy defines how an engineering team will ensure software quality across the entire development lifecycle. It goes beyond individual test types and addresses how testing fits into CI/CD, how to measure coverage, how to handle environments, and how to manage technical debt related to testing. A good strategy balances speed of delivery with confidence in quality.

## Interview Questions

### Question 1: How do you decide what to test? (How much is enough?)
* **Difficulty:** Medium
* **Frequency:** High
* **Companies:** All major tech companies

**Excellent Answer:**
Deciding what to test is about risk management. I follow the test pyramid, aiming for high unit test coverage of business logic and algorithms, moderate integration coverage of database/API boundaries, and minimal E2E tests for critical user journeys (CUJs). I don't aim for 100% code coverage, as the law of diminishing returns applies, and it often leads to low-quality tests. Instead, I prioritize testing:
1. Complex business logic.
2. Historically buggy areas of the codebase.
3. Code that is frequently changed.
4. Security and authorization flows.
"Enough" is reached when the team has confidence to deploy to production at any time without manual regression testing.

**Common Mistakes:**
* Fixating on a specific code coverage percentage (like strictly requiring 90%).
* Treating all parts of the application as equally risky.

### Question 2: How do you handle flaky tests in a CI pipeline?
* **Difficulty:** Hard
* **Frequency:** High
* **Companies:** Uber, Meta, GitHub

**Excellent Answer:**
Flaky tests destroy trust in the CI suite; developers will start ignoring failures if they believe it's "just a flake." My strategy is:
1. **Quarantine:** As soon as a test is identified as flaky, it should be quarantined (moved out of the blocking CI path) and a ticket created to fix it.
2. **Investigation:** Root causes are usually race conditions, improper handling of async operations, shared state, or reliance on network timing.
3. **Resolution:** Fix the underlying issue (e.g., replacing fixed sleeps with polling/waiting for states). If a test is inherently unreliable and cannot be fixed, it is often better to delete it or rewrite it at a lower level of the test pyramid than to keep a flaky test.

**Common Mistakes:**
* Automatically retrying tests in CI without logging or fixing the underlying issue, masking the problem.
* Blaming the testing tool rather than test design.

## Real-World Applications
* **CI/CD Pipeline Design:** Configuring a GitHub Actions or Jenkins pipeline to run fast tests on every commit and slower E2E tests only before merging to the main branch.
* **Release Management:** Using automated test results as a go/no-go gate for automated deployments to staging or production environments.

## Practice Problems

| Problem | Type | Focus | Difficulty |
| :--- | :--- | :--- | :--- |
| Design a testing pipeline for a SaaS product | Architecture | CI/CD, environments | Medium |
| Propose a plan to fix a legacy app with no tests | Strategy | Refactoring, characterization tests | Hard |

## Hiring Manager Perspective
Managers are looking for maturity. They want engineers who understand that testing is an economic activity—we spend time writing tests to save time fixing bugs and to enable faster feature development. They appreciate candidates who talk about ROI (Return on Investment) of tests, developer experience, and maintaining a fast CI pipeline.

## AI Interview Coach
**Prompt for ChatGPT/Claude/Gemini:**
> "Act as a Director of Engineering. Ask me to outline a testing strategy for a newly formed team building a critical microservice from scratch. Push back on my ideas regarding code coverage metrics and how to handle testing in production."
