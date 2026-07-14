# Unit Testing

## Overview
Unit testing involves testing individual components or functions of a software application in isolation. The primary goal is to validate that each unit of the software performs as designed. Unit tests should be fast, deterministic, and isolated from external dependencies like databases, file systems, or network calls, often achieved through mocking or stubbing.

## Interview Questions

### Question 1: What is the difference between a mock and a stub?
* **Difficulty:** Medium
* **Frequency:** High
* **Companies:** Microsoft, Netflix, Uber

**Excellent Answer:**
Both mocks and stubs are test doubles used to isolate the unit being tested, but they serve different purposes. A **stub** simply provides canned answers to calls made during the test, usually not responding at all to anything outside what's programmed for the test. It's used for state verification. A **mock**, on the other hand, is pre-programmed with expectations which form a specification of the calls they are expected to receive. It's used for behavior verification (e.g., asserting that a specific method was called exactly once with specific parameters).

**Common Mistakes:**
* Confusing the two terms or using them interchangeably.
* Over-mocking, which leads to brittle tests that break upon internal refactoring even if the external behavior hasn't changed.

### Question 2: Explain Test-Driven Development (TDD).
* **Difficulty:** Medium
* **Frequency:** Medium
* **Companies:** ThoughtWorks, IBM, Apple

**Excellent Answer:**
TDD is a software development process relying on a very short development cycle: first, the developer writes an (initially failing) automated test case that defines a desired improvement or new function, then produces the minimum amount of code to pass that test, and finally refactors the new code to acceptable standards. The cycle is often summarized as "Red-Green-Refactor." TDD helps ensure that code is testable by design and acts as executable documentation.

**Common Mistakes:**
* Believing TDD is just writing tests before code without understanding the refactoring step.
* Stating that TDD must strictly be followed 100% of the time, rather than acknowledging it as a tool that is highly effective for complex logic but maybe overkill for simple CRUD operations.

## Real-World Applications
* **Complex Algorithm Verification:** Writing unit tests for a sorting algorithm or a tax calculation engine to ensure all edge cases (e.g., empty arrays, negative numbers) are handled correctly.
* **Isolating Bug Fixes:** When a bug is reported, writing a failing unit test that reproduces the bug, then fixing the code to make the test pass, ensuring the bug never returns.

## Practice Problems

| Problem | Type | Focus | Difficulty |
| :--- | :--- | :--- | :--- |
| Write unit tests for a string calculator | Coding | TDD, edge cases | Easy |
| Test a function that fetches user data from a DB | Practical | Mocking dependencies | Medium |

## Hiring Manager Perspective
Managers want engineers who write unit tests that are resilient and meaningful. They watch out for candidates who write tests that are too tied to implementation details (which break on refactoring) or tests that assert nothing of value just to increase code coverage metrics. 

## AI Interview Coach
**Prompt for ChatGPT/Claude/Gemini:**
> "I want to practice answering questions about unit testing. Ask me to explain the concepts of mocking, stubbing, and dependency injection in the context of unit testing. After I answer, provide constructive feedback on how I can sound more senior."
