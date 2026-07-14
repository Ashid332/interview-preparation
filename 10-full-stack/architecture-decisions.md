# Architecture Decisions

## Overview
Architecture decisions involve choosing the overarching structure of an application. This includes deciding between monoliths and microservices, selecting serverless vs. containerized deployments, and choosing the right database (SQL vs. NoSQL) based on business requirements.

## Interview Questions
* **Difficulty:** Hard
* **Frequency:** High (especially for senior roles)
* **Companies:** Tech companies scaling their operations.

### Excellent Answer
"We initially built a monolith because speed to market was critical. However, as the team grew and the reporting module started consuming too many resources, we extracted it into a separate microservice using a read-replica database, improving overall system stability."

### Common Mistakes
* Recommending microservices for a simple, low-traffic application (premature optimization).
* Failing to articulate the CAP theorem when discussing distributed databases.
* Ignoring the operational overhead of complex architectures (e.g., observability, deployment pipelines).

## Real-World Applications
* Transitioning an application from a traditional VPS deployment to Kubernetes.
* Choosing between PostgreSQL and MongoDB for a new startup product.
* Implementing a caching layer (Redis/Memcached) to reduce database load.

## Practice Problems

| Problem | Topic | Difficulty | Focus |
| :--- | :--- | :--- | :--- |
| Monolith to Microservices | Architecture | Hard | Migration Strategy |
| Choose a Database | DB Design | Medium | SQL vs NoSQL |
| Scaling for Black Friday | Scalability | Hard | Load balancing/Caching |

## Hiring Manager Perspective
"Every architecture decision is a trade-off. If a candidate says 'Microservices are always better,' they lack experience. I want to hear about the pain points they've experienced with different architectures."

## AI Interview Coach

**Prompt for ChatGPT/Claude/Gemini:**
> "Present me with a business scenario where a company is experiencing growing pains with their current tech stack. Ask me to propose a new architecture. Evaluate my response based on trade-offs, scalability, and maintainability."
