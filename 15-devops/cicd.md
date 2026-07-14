# CI/CD (Continuous Integration & Continuous Deployment)

## Overview
CI/CD forms the backbone of modern software delivery. Continuous Integration involves frequently merging code changes into a central repository where automated builds and tests are run. Continuous Deployment (or Delivery) automates the release of that validated code to staging or production environments.

## Interview Questions

### Question 1: What is the difference between Continuous Delivery and Continuous Deployment?
* **Difficulty:** Easy
* **Frequency:** High
* **Companies:** GitHub, GitLab, Meta

**Excellent Answer:**
Continuous Delivery means that every change that passes all stages of your production pipeline is released to a staging environment and is ready to be deployed to production, but the final deployment requires a manual approval step. Continuous Deployment takes this one step further by eliminating the manual approval; every change that passes automated tests is automatically pushed to production without human intervention.

**Common Mistakes:**
- Using the terms interchangeably.
- Failing to mention that both require a highly robust automated testing suite to be effective.

## Real-World Applications
CI/CD pipelines (via tools like GitHub Actions, Jenkins, GitLab CI) are used to automate code linting, unit testing, security scanning (SAST/DAST), and infrastructure provisioning before delivering code to end users.

## Practice Problems
| Problem | Description | Complexity | Link |
| --- | --- | --- | --- |

## Hiring Manager Perspective
A good candidate treats their CI/CD pipeline as a critical production system. Hiring managers look for a focus on pipeline speed (fast feedback loops), reliability, and security practices (like secure credential management in pipelines).

## AI Interview Coach
**ChatGPT/Claude/Gemini Prompt:**
> "Act as a Staff Engineer. I am going to explain how I would build a CI/CD pipeline from scratch for a containerized application. Critique my design for security flaws and performance bottlenecks."
