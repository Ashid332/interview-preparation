# Git & Version Control

## Overview
Git is a distributed version control system that tracks changes in source code. It is designed to handle everything from small to very large projects with speed and efficiency. Mastery of Git is essential for collaborating in almost any modern engineering team.

## Interview Questions

### Question 1: What is a merge conflict, and how do you resolve one? Explain `git rebase` vs `git merge`.
* **Difficulty:** Medium
* **Frequency:** Very High
* **Companies:** All Software Companies

**Excellent Answer:**
A merge conflict happens when two branches have competing commits on the same lines of a file, or one branch edits a file while another deletes it. To resolve it, I open the affected files, decide which changes to keep using the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`), save the files, and commit the resolution. 
Regarding `merge` vs `rebase`: `git merge` takes two branches and joins them with a merge commit, preserving the exact history. `git rebase` moves the base of the current branch to the tip of the target branch, rewriting history to create a clean, linear commit history without merge commits.

**Common Mistakes:**
- Recommending `git rebase` on shared, public branches (which disrupts other developers).
- Not understanding how to abort a messy rebase or merge using `--abort`.

## Real-World Applications
Used daily by developers to branch out for new features, track bugs, review code via Pull Requests, and enforce commit hygiene (e.g., conventional commits).

## Practice Problems
| Problem | Description | Complexity | Link |
| --- | --- | --- | --- |

## Hiring Manager Perspective
Beyond basic commands, managers look for developers who understand branch strategies (like GitFlow vs Trunk-Based Development) and who write clear, descriptive commit messages. Knowing how to recover from mistakes (using `git reflog`) is highly valued.

## AI Interview Coach
**ChatGPT/Claude/Gemini Prompt:**
> "Act as a strict code reviewer. Quiz me on advanced Git commands including interactive rebasing, bisecting for bug hunting, and recovering lost commits."
