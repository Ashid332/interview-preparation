# React Cheat Sheet

## Key Concepts
| Concept | Description |
|---|---|
| Virtual DOM | In-memory representation of the real DOM. React diffs them to minimize expensive DOM updates. |
| Components | Reusable, self-contained UI building blocks (Functional vs Class). |
| Hooks | Functions that let you "hook into" React state and lifecycle features from function components. |
| Context API | Mechanism for passing data deeply through the component tree without prop drilling. |

## Must-Know Items
- Component Lifecycle (Mounting, Updating, Unmounting) and how `useEffect` maps to it.
- State management (`useState`, `useReducer`, Redux, Zustand).
- Performance optimization (`React.memo`, `useMemo`, `useCallback`).
- Rules of Hooks (only call at the top level, only in React functions).

## Common Interview Questions (Quick)
1. What is the Virtual DOM and how does reconciliation work?
2. Explain the difference between `useEffect` and `useLayoutEffect`.
3. How do you prevent unnecessary re-renders?
4. What is prop drilling and how do you avoid it?
5. Write a custom hook to fetch data.

## Critical Commands/Patterns
```jsx
// Custom Hook Pattern
function useFetch(url) {
  const [data, setData] = useState(null);
  useEffect(() => {
    let mounted = true;
    fetch(url).then(r => r.json()).then(d => { if(mounted) setData(d) });
    return () => { mounted = false }; // Cleanup
  }, [url]);
  return data;
}
```

## Decision Framework
- **State Location:** Keep state local if only one component needs it. Lift state up if siblings need it. Use Context/Redux if state is global (theme, user auth).
- **Optimization:** Use `useMemo` for expensive calculations. Use `useCallback` when passing functions to optimized child components. Don't optimize prematurely.

## Common Mistakes
- Mutating state directly (e.g., `state.count = 1`) instead of using setters (`setState`).
- Missing dependency array in `useEffect`, causing infinite loops.
- Overusing Context for high-frequency state updates (causes widespread re-renders).
- Forgetting cleanup functions in `useEffect` (memory leaks).

## One-Minute Review
- React is a UI library focused on component composition and declarative rendering via Virtual DOM. Master Hooks, state lifting, and basic performance optimizations to ace React interviews.
