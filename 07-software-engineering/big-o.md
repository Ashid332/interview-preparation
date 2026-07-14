# Big O Notation

## Overview
Big O Notation describes the performance or complexity of an algorithm relative to the input size. It provides a high-level understanding of the time (execution time) and space (memory used) required, which is essential for writing scalable code.

## Interview Questions
* **Difficulty:** Easy to Medium
* **Frequency:** Extremely High (expected in every coding interview)
* **Companies:** Universal.

### Excellent Answer
"This algorithm has a time complexity of O(N log N) because we are dividing the array in half at each step (log N) and iterating through the elements (N). The space complexity is O(N) because we need an auxiliary array of size N to store the intermediate results."

### Common Mistakes
* Confusing worst-case, average-case, and best-case complexities.
* Forgetting to drop constants (e.g., saying O(2N) instead of O(N)).
* Overlooking the space complexity of the recursive call stack.

## Real-World Applications
* Predicting how an application will perform when scaling from 10,000 to 10 million users.
* Identifying performance bottlenecks in legacy code.
* Choosing between two third-party libraries based on their algorithmic efficiency.

## Practice Problems

| Problem | Topic | Difficulty | Focus |
| :--- | :--- | :--- | :--- |
| Analyze Loops | Time Complexity | Easy | Nested loops |
| Recursive Fibonacci | Time/Space | Medium | Exponential vs Linear |
| Space of BFS | Space Complexity | Medium | Max queue size |

## Hiring Manager Perspective
"A candidate who cannot articulate the Big O of their code is a red flag. It shows they might write code that works on their local machine but will crash production systems under heavy load."

## AI Interview Coach

**Prompt for ChatGPT/Claude/Gemini:**
> "Provide me with 5 different code snippets in Python/Java. For each snippet, ask me to determine the time and space complexity in Big O notation. Wait for my answer before providing the correct response and explanation."
