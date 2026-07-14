# Data Structures & Algorithms Cheat Sheet

## Key Concepts
| Concept | Description |
|---|---|
| Big O Notation | Describes the worst-case time and space complexity of an algorithm. |
| Hash Tables | Key-value store with O(1) average time complexity for lookup/insert/delete. |
| Trees & Graphs | Non-linear data structures. Trees have root/leaves. Graphs have vertices/edges. |
| Dynamic Programming | Breaking a complex problem down into simpler overlapping subproblems and caching results (memoization). |

## Must-Know Items
- Array/String manipulation (Two Pointers, Sliding Window).
- BFS (Breadth-First Search) using Queues and DFS (Depth-First Search) using Stacks/Recursion.
- Sorting complexities: QuickSort (O(N log N)), MergeSort (O(N log N)).
- Binary Search (O(log N)) on sorted arrays.

## Common Interview Questions (Quick)
1. Reverse a Linked List.
2. Two Sum (use a Hash Map).
3. Valid Parentheses (use a Stack).
4. Number of Islands (Graph DFS/BFS).
5. Lowest Common Ancestor of a Binary Tree.

## Critical Commands/Patterns
*Sliding Window Pattern (Longest Substring without repeating characters):*
```python
def lengthOfLongestSubstring(s: str) -> int:
    char_set = set()
    left = 0
    res = 0
    for right in range(len(s)):
        while s[right] in char_set:
            char_set.remove(s[left])
            left += 1
        char_set.add(s[right])
        res = max(res, right - left + 1)
    return res
```

## Decision Framework
- **Unsorted Array needing lookups?** -> Put in a Hash Set/Map (O(N) time/space).
- **Sorted Array?** -> Binary Search or Two Pointers.
- **Tree/Graph traversal?** -> Shortest path = BFS. Exhaustive search = DFS.
- **Finding Top K elements?** -> Min/Max Heap (Priority Queue).

## Common Mistakes
- Not communicating your thought process before writing code.
- Ignoring edge cases (empty arrays, null nodes, negative numbers).
- Forgetting to mention space complexity when analyzing your solution.
- Modifying arrays while iterating over them.

## One-Minute Review
- Master the core patterns: Two Pointers, Sliding Window, DFS/BFS, and Heaps. Always clarify requirements, state the brute force solution briefly, then optimize using standard data structures.
