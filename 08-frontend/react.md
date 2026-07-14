# React.js Interview Guide

## Overview
React is the dominant library for building user interfaces. Interviews test your deep understanding of the component lifecycle, hooks (useState, useEffect, useMemo), state management, performance optimization (re-renders), and React's internal mechanisms like the Virtual DOM and Reconciliation.

## Interview Questions

### Question 1: How does React's Virtual DOM work, and how does the reconciliation process optimize updates?
**Difficulty:** Medium | **Frequency:** High | **Companies:** Meta, Amazon, Netflix

**Excellent Answer:**
The Virtual DOM is a lightweight JavaScript representation of the actual DOM. Direct DOM manipulation is slow, so React batches updates using the VDOM.
1. When state or props change, React creates a new Virtual DOM tree.
2. React then compares this new tree with the previous Virtual DOM tree (a process called *diffing*).
3. React uses a heuristic O(n) algorithm for diffing, assuming:
   - Elements of different types will produce different trees.
   - Developers can hint at which child elements are stable across renders using a `key` prop.
4. Once the diffing is complete, React calculates the minimum number of changes needed (the "patch") and updates the real DOM in a single batched operation. This is the *Reconciliation* process.

**Common Mistakes:**
- Stating the Virtual DOM is faster than the real DOM (it's not; it's a tool to *prevent* unnecessary real DOM updates).
- Failing to explain the importance of the `key` prop in the diffing algorithm.

### Question 2: Explain the lifecycle of a React Hook (`useEffect`) and how to avoid memory leaks.
**Difficulty:** Medium | **Frequency:** Very High | **Companies:** Google, Atlassian, Stripe

**Excellent Answer:**
`useEffect` allows you to perform side effects in functional components. Its lifecycle depends on the dependency array:
- **No array:** Runs after every render.
- **Empty array `[]`:** Runs once after the initial mount (similar to `componentDidMount`).
- **Array with values `[x, y]`:** Runs when mounted, and re-runs if `x` or `y` change between renders.
To prevent memory leaks (e.g., lingering event listeners, active intervals, or async calls resolving on unmounted components), `useEffect` can return a **cleanup function**. React runs this cleanup function before the component unmounts, and before re-running the effect on subsequent renders.

**Common Mistakes:**
- Forgetting the cleanup function, leading to multiple event listeners being attached.
- Mismanaging the dependency array, causing infinite re-render loops.

## Real-World Applications
- **Complex Forms:** Managing multi-step form state and validation without causing the entire page to re-render.
- **Real-time Dashboards:** Efficiently rendering high-frequency data updates using `useMemo`, `useCallback`, and `React.memo` to prevent unnecessary component renders.
- **Micro-frontends:** Isolating different parts of an application using React components and Context for distinct feature teams.

## Practice Problems

| Problem | Focus Area | Difficulty |
|---------|------------|------------|
| Build a Custom `useFetch` Hook | Hooks, Async operations, State | Medium |
| Implement an infinite scrolling list | Intersection Observer, State | Hard |
| Create an Accordion Component | Compound components, Context API | Medium |
| Fix a performance issue in a provided React app | Profiler, `useMemo`, `React.memo` | Hard |

## Hiring Manager Perspective
"In React interviews, I look for candidates who understand that React is just JavaScript. If a candidate relies too heavily on magic without understanding closures (which are crucial for understanding stale state in Hooks), they will struggle. I also highly value candidates who naturally prioritize accessibility (a11y) in their component design."

## AI Interview Coach

**Prompt for ChatGPT/Claude/Gemini:**
> "Act as a Lead Frontend Engineer reviewing a React Pull Request. Provide me with a snippet of React code that contains subtle bugs related to stale closures in `useEffect` and unnecessary re-renders. Ask me to identify the bugs and rewrite the component to be performant and bug-free."
