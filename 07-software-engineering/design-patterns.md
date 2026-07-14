# Design Patterns

## Overview
Design patterns are typical solutions to common problems in software design. They represent best practices evolved over time. Common patterns include Singleton, Factory, Observer, Strategy, and Decorator.

## Interview Questions
* **Difficulty:** Medium
* **Frequency:** High (especially for mid to senior roles)
* **Companies:** Enterprise software, Java/C# shops, modern web frameworks.

### Excellent Answer
"I used the Observer pattern here because we have a one-to-many dependency. When the state of the central object changes, all its dependents need to be notified automatically, which perfectly fits our event-driven architecture."

### Common Mistakes
* Over-engineering: using patterns where simple procedural code would suffice.
* Misunderstanding the Singleton pattern and its implications on global state and testing.
* Not knowing how modern languages implement these patterns natively (e.g., callbacks vs. Observer).

## Real-World Applications
* **Observer:** UI event listeners (React, Vue), publish/subscribe systems.
* **Factory:** Creating different types of database connections or UI components dynamically.
* **Singleton:** Configuration managers, logging services (use with caution).

## Practice Problems

| Problem | Topic | Difficulty | Focus |
| :--- | :--- | :--- | :--- |
| Implement Logger | Singleton | Easy | Thread safety |
| Event Emitter | Observer | Medium | Pub/Sub logic |
| Payment Gateway | Strategy | Medium | Interchangeable algos |

## Hiring Manager Perspective
"I appreciate candidates who know design patterns but know when NOT to use them. Patterns should facilitate readability and maintainability, not obscure the business logic with abstract classes."

## AI Interview Coach

**Prompt for ChatGPT/Claude/Gemini:**
> "Act as a software architect. Present a messy, tightly-coupled code scenario. Ask me to refactor it using an appropriate design pattern. Evaluate my choice of pattern and the trade-offs I considered."
