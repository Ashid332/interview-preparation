# Software Engineer Interview Learning Path

## Role Overview
Software Engineers (SWE) are the backbone of modern technology companies. This role demands strong problem-solving skills, proficiency in data structures and algorithms, and the ability to design scalable systems. This 12-week path prepares you for generalist SWE roles at top-tier technology companies.

## Prerequisites

| Skill Area | Expected Proficiency Level | Resources for Review |
|------------|----------------------------|----------------------|
| Programming Language | Advanced (Java, Python, C++, or Go) | Language-specific documentation |
| Basic Data Structures | Intermediate (Arrays, Strings, Hash Maps) | Standard CS curriculum |
| Time/Space Complexity | Intermediate (Big O Notation) | Cracking the Coding Interview |

## Path Overview

```mermaid
gantt
    title Software Engineer 12-Week Preparation Plan
    dateFormat  w
    axisFormat %W
    section Fundamentals
    Data Structures       :a1, 0, 3w
    Algorithms            :a2, after a1, 3w
    section System Design
    High-Level Design     :a3, after a2, 3w
    section Behavioral & Polish
    Mock Interviews       :a4, after a3, 2w
    Final Review          :a5, after a4, 1w
```

## Weekly Roadmap

### Weeks 1-3: Advanced Data Structures
Focus on mastering foundational data structures essential for coding interviews.

| Week | Focus Area | Key Concepts | Practice Goal (LeetCode) |
|------|------------|--------------|---------------------------|
| 1 | Arrays & Strings | Sliding Window, Two Pointers, Prefix Sum | 15 Easy, 5 Medium |
| 2 | Hash Maps & Sets | Hashing collisions, Frequency maps | 10 Easy, 10 Medium |
| 3 | Linked Lists & Stacks | Reversals, Cycle detection, Monotonic Stacks | 5 Easy, 15 Medium |

### Weeks 4-6: Algorithms & Patterns
Transition to algorithmic problem solving.

| Week | Focus Area | Key Concepts | Practice Goal (LeetCode) |
|------|------------|--------------|---------------------------|
| 4 | Trees & Graphs | DFS, BFS, Binary Search Trees, Topological Sort | 20 Medium |
| 5 | Dynamic Programming | Memoization, Tabulation, Knapsack, LCS | 5 Easy, 15 Medium |
| 6 | Sorting & Searching | Binary Search, Merge Sort, Quick Select | 15 Medium, 5 Hard |

### Weeks 7-9: System Design Fundamentals
Understanding how to build scalable systems.

| Week | Focus Area | Key Concepts | Action Item |
|------|------------|--------------|-------------|
| 7 | Core Concepts | CAP Theorem, Load Balancing, Caching, CDNs | Read "Designing Data-Intensive Applications" (Ch 1-3) |
| 8 | Databases & Storage| SQL vs NoSQL, Sharding, Replication | Design a URL Shortener |
| 9 | Distributed Systems | Microservices, Message Queues (Kafka), Eventual Consistency | Design a Chat Application (e.g., WhatsApp) |

### Weeks 10-12: Behavioral & Mock Interviews
Polishing communication and final preparations.

| Week | Focus Area | Key Concepts | Action Item |
|------|------------|--------------|-------------|
| 10 | Behavioral (STAR) | Leadership principles, Conflict resolution | Draft 10 STAR stories |
| 11 | Mock Interviews | Time management, Communication under pressure | Conduct 3 technical mock interviews |
| 12 | Final Review | Weak area targeting, Rest & Recovery | Revisit failed problems, limit new content |

## Milestones & Checkpoints

- [ ] **End of Week 3:** Can comfortably solve Medium level Array/String problems within 25 minutes.
- [ ] **End of Week 6:** Can recognize common algorithmic patterns (e.g., DP vs Greedy) upon reading a prompt.
- [ ] **End of Week 9:** Can confidently sketch out a high-level architecture for a standard web application on a whiteboard.
- [ ] **End of Week 11:** Consistently passing mock interviews with clear communication.

## Company Recommendations

- **FAANG (Meta, Amazon, Apple, Netflix, Google):** Emphasize LeetCode Hard and complex, large-scale System Design.
- **Startups (Series B/C):** Focus heavily on practical coding, API design, and cultural fit/ownership.
- **Fintech (Stripe, Plaid):** Focus on consistency, transactional database integrity, and error handling.

## Interview Readiness Checklist

- [ ] Consistently solve LeetCode Mediums in < 30 mins.
- [ ] System design framework memorized (Requirements -> Capacity -> High Level -> Deep Dive).
- [ ] 5-7 robust STAR stories prepared and rehearsed.
- [ ] Familiar with the target company's core values and recent product launches.
