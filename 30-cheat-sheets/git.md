# Git Cheat Sheet

## Key Concepts
| Concept | Description |
|---|---|
| Working Directory | Where you are currently modifying files. |
| Staging Area (Index) | A pre-commit holding area. |
| Repository (HEAD) | Where your committed snapshots live. |
| Rebase | Moving a sequence of commits to a new base commit, creating a linear history. |

## Must-Know Items
- Difference between `git merge` and `git rebase`.
- How to resolve merge conflicts.
- Undoing changes (`reset`, `revert`, `checkout`/`restore`).
- Branching strategies (GitFlow, GitHub Flow).

## Common Interview Questions (Quick)
1. What is the difference between `git pull` and `git fetch`?
2. How do you squash multiple commits into one?
3. What is the difference between `git reset --soft` and `git reset --hard`?
4. What is `git cherry-pick` used for?

## Critical Commands/Patterns
```bash
# Squash last 3 commits
git rebase -i HEAD~3

# Undo last commit but keep changes in working directory
git reset --soft HEAD~1

# Discard all local changes
git reset --hard HEAD
git clean -fd
```

## Decision Framework
- **Merge vs Rebase:** Use `merge` when pulling features into `main` to preserve history of *when* things happened. Use `rebase` when updating your feature branch from `main` to keep a clean, linear history. Never rebase public/shared branches.

## Common Mistakes
- Committing sensitive data (always use `.gitignore` and tools like `git-filter-repo` to fix if leaked).
- Pushing directly to `main` instead of using PRs.
- Writing poor commit messages ("fix", "updates").

## One-Minute Review
- Git is a distributed version control system. Understand the 3 trees (Working, Staging, HEAD), branching, rebasing vs merging, and how to safely undo mistakes.
