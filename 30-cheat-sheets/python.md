# Python Cheat Sheet

## Key Concepts
| Concept | Description |
|---|---|
| GIL (Global Interpreter Lock) | Mutex that allows only one thread to hold the control of the Python interpreter (in CPython). |
| List Comprehensions | Concise way to create lists based on existing lists. |
| Generators | Functions that yield values one at a time using `yield`, saving memory. |
| Decorators | Functions that modify the behavior of another function. |

## Must-Know Items
- Mutable vs Immutable types (List/Dict vs Tuple/String).
- Differences between shallow copy and deep copy.
- Dunder/Magic methods (`__init__`, `__str__`, `__eq__`).
- Context Managers (`with` statement) for resource management.

## Common Interview Questions (Quick)
1. What is the GIL and how does it affect concurrency?
2. How are arguments passed in Python (pass by assignment/object reference)?
3. What is a decorator? Write a simple execution-timer decorator.
4. Difference between a list and a tuple.

## Critical Commands/Patterns
```python
# List Comprehension
squares = [x**2 for x in range(10) if x % 2 == 0]

# Generator
def fibonacci(n):
    a, b = 0, 1
    for _ in range(n):
        yield a
        a, b = b, a + b

# Decorator
def timer(func):
    def wrapper(*args, **kwargs):
        # start time
        res = func(*args, **kwargs)
        # end time, print difference
        return res
    return wrapper
```

## Decision Framework
- **Concurrency:** Use `threading` for I/O-bound tasks. Use `multiprocessing` for CPU-bound tasks to bypass the GIL. Use `asyncio` for high-concurrency network I/O.
- **Iteration:** Use generators when dealing with large datasets to save memory instead of storing in lists.

## Common Mistakes
- Using mutable default arguments in functions (e.g., `def append(item, lst=[]):`).
- Misunderstanding variable scope and the `global` or `nonlocal` keywords.
- Catching general exceptions (`except Exception:`) without logging or handling them properly.

## One-Minute Review
- Python values readability (`import this`). Understand the GIL, decorators, generators, and data structures. It's heavily used in data, AI, and backend (Django/FastAPI).
