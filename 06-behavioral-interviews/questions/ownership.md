# Ownership

## Why Interviewers Ask This
Ownership means treating the product, code, and company as if they were your own. Interviewers want to see that you don't just "write code and throw it over the wall," but that you care about the end-to-end user experience, code quality, and business outcomes.

## Evaluation Criteria

| Criteria | Description |
| :--- | :--- |
| **Proactivity** | Does the candidate identify and fix issues before being told? |
| **End-to-End Care** | Do they care about testing, deployment, and monitoring, not just coding? |
| **Accountability** | Do they take responsibility for outcomes, both good and bad? |
| **Business Alignment**| Do they understand how their work impacts the broader business goals? |

## Weak Answer
"I noticed that our build pipeline was really slow, but that's the DevOps team's responsibility, so I just waited for them to fix it. Eventually, they did, and things got faster."
*Critique: Classic "not my job" mentality. Shows zero ownership or proactivity.*

## Average Answer
"I saw a bug in production where users couldn't log in sometimes. I created a Jira ticket for it and assigned it to the team that owns the authentication service. They fixed it a few days later."
*Critique: Better because they reported it, but still lacks deep ownership. They handed the problem off rather than driving it to resolution.*

## Strong Answer (STAR)
**Situation**: "While investigating a minor bug in my team's microservice, I noticed a separate, critical vulnerability in a legacy authentication service owned by a different, currently understaffed team."
**Task**: "I needed to ensure this vulnerability was patched immediately, even though it wasn't in my team's domain or on my sprint board."
**Action**: "I immediately alerted the engineering director and the security team. Knowing the owning team was swamped, I offered to draft the fix myself. I spent the evening diving into their codebase, wrote a patch, and submitted a PR. I then coordinated directly with their lead engineer to get it reviewed and guided it through the deployment pipeline the next morning."
**Result**: "The vulnerability was patched before it could be exploited. Furthermore, I identified that the lack of automated security scanning caused the oversight, so I later volunteered to help integrate a scanning tool across all our legacy repos, preventing similar issues."

## Follow-Up Questions
* "Tell me about a time you went above and beyond your job description."
* "How do you balance taking ownership of issues with not stepping on other teams' toes?"
* "Describe a time you identified a problem but lacked the authority to fix it directly. What did you do?"

## Hiring Manager Notes
Engineers with high ownership are low-maintenance and high-impact. I look for the phrase "I saw a problem, so I fixed it" (or drove the fix). They blur the lines of their job description to ensure the company succeeds.

## Scoring Rubric

| Rating | Description |
| :--- | :--- |
| **1 - Poor** | Exhibits a "not my job" attitude; ignores problems outside immediate scope. |
| **2 - Fair** | Reports issues but relies entirely on others to solve them. |
| **3 - Good** | Takes responsibility for their own code end-to-end; occasionally helps elsewhere. |
| **4 - Excellent** | Proactively identifies and solves systemic or cross-team problems; drives initiatives independently. |

## Practice Exercise
Recall a time when you found a broken process or piece of code that no one was paying attention to. Write a STAR response showing how you took the initiative to resolve it end-to-end.

## AI Roleplay Prompt
```text
Act as a VP of Engineering. Ask me: "Tell me about a time you saw an opportunity to improve something outside of your direct responsibilities." Evaluate my response based on my proactivity, end-to-end care, and impact.
```
