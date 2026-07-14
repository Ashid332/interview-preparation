# Object-Oriented Programming (OOP)

## Overview
OOP is a programming paradigm based on the concept of "objects," which can contain data and code. The four main pillars are Encapsulation, Abstraction, Inheritance, and Polymorphism.

## Interview Questions
* **Difficulty:** Medium
* **Frequency:** High
* **Companies:** Amazon, Microsoft, financial institutions.

### Excellent Answer
"Polymorphism allows objects of different classes to be treated as objects of a common superclass. This makes the code highly extensible. For example, a `draw()` method can behave differently whether it's called on a `Circle` or a `Square` object."

### Common Mistakes
* Favoring inheritance over composition (leading to fragile base class problems).
* Creating "God objects" that do too many things, violating the Single Responsibility Principle.
* Failing to explain the practical benefits of Encapsulation (protecting state).

## Real-World Applications
* Designing complex software systems with many interacting entities (e.g., video games, simulation software).
* Structuring large enterprise applications in Java, C#, or C++.
* Designing APIs where internal implementations can change without breaking client code (Abstraction).

## Practice Problems

| Problem | Topic | Difficulty | Focus |
| :--- | :--- | :--- | :--- |
| Parking Lot Design | OOD | Medium | Classes & Interfaces |
| Deck of Cards | OOD | Easy | Inheritance/Composition |
| Vending Machine | OOD | Hard | State Management |

## Hiring Manager Perspective
"OOP interviews are less about remembering textbook definitions and more about seeing how you model the real world in code. I look for clean separation of concerns and interfaces that make sense."

## AI Interview Coach

**Prompt for ChatGPT/Claude/Gemini:**
> "Give me an Object-Oriented Design prompt (like designing a Library Management System). I will provide the classes, attributes, methods, and relationships. Critique my design based on SOLID principles."
