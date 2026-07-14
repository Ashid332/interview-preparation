# Style Guide

To maintain a consistent, high-quality experience for readers, all contributions must adhere to this Style Guide.

## 1. Editorial Voice
*   **Persona:** Write from the perspective of a Senior Engineering Manager or Staff Engineer.
*   **Tone:** Direct, authoritative, encouraging, but relentlessly practical.
*   **No Fluff:** Avoid generic introductions. Do not write "In this section we will discuss...". Dive straight into the value.
*   **No Clichés:** Avoid phrases like "In today's fast-paced digital world..." or "Communication is key."

## 2. Technical Topic Page Template

Every file in the Technical Library (`07` through `23`) must follow this exact structure:

```markdown
# [Topic Name]

## Overview
[1-2 sentences of high-impact definition. No filler.]

## Interview Questions

### Q1: [The Question]
**Difficulty:** [Easy/Medium/Hard] | **Frequency:** [Low/Medium/High] | **Companies:** [e.g., Google, Stripe]

**Excellent Answer:**
[The answer, prioritizing the 'why' over just the 'what']

**Common Mistakes:**
- [Mistake 1]
- [Mistake 2]

## Real-World Applications
- [Concrete Example 1]
- [Concrete Example 2]

## Practice Problems
| Problem | Difficulty | Focus Area | Link/Description |
|---|---|---|---|
| [Name] | [Diff] | [Focus] | [Description] |

## Hiring Manager Perspective
[What interviewers are *actually* looking for behind closed doors when evaluating this topic.]

## AI Interview Coach
[A prompt the user can paste into ChatGPT/Claude to simulate an interview on this topic.]
```

## 3. Formatting Standards
*   **Headers:** Use Sentence case for content (e.g., `## Common mistakes`), Title Case for standard sections (e.g., `## Hiring Manager Perspective`).
*   **Bold Text:** Use `**bold**` to emphasize keywords, especially in long paragraphs.
*   **Callouts:** Use GitHub alerts for critical information:
    *   `> [!NOTE]` for interesting context.
    *   `> [!TIP]` for actionable interview hacks.
    *   `> [!WARNING]` for common traps or red flags.
*   **Code Blocks:** Always specify the language (e.g., ```python).
*   **Diagrams:** Use `mermaid` for flowcharts, Gantt charts, and architecture diagrams. Do not use external image links unless absolutely necessary.
