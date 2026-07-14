# Problem Solving

## Why Interviewers Ask This
Engineering is fundamentally about solving problems. Interviewers want to see your analytical process, your creativity, how you break down complex ambiguous issues, and how you persist when the obvious solutions don't work.

## Evaluation Criteria

| Criteria | Description |
| :--- | :--- |
| **Analytical Thinking** | How logically does the candidate approach the problem? |
| **Creativity** | Can they think outside the box when standard methods fail? |
| **Persistence** | Do they give up easily or dig deep to find the root cause? |
| **Resourcefulness** | Do they effectively utilize tools, data, and colleagues? |

## Weak Answer
"We had a bug where the app kept crashing. I spent a whole day looking at the code but couldn't figure it out. Eventually, I just asked a senior engineer, and he told me it was a memory leak, so I fixed it based on his instructions."
*Critique: Lacks initiative, analytical process, and reliance on others without attempting a structured debugging approach.*

## Average Answer
"Customers were complaining about slow load times. I looked at the database queries and saw one was taking over 5 seconds. I added an index to the table, and that sped up the query, solving the problem."
*Critique: Identifies a problem and a solution, but lacks depth regarding the investigation process or consideration of alternative causes.*

## Strong Answer (STAR)
**Situation**: "Our main service started experiencing intermittent latency spikes during peak hours, causing timeouts for about 5% of users. The basic metrics didn't show any obvious CPU or memory bottlenecks."
**Task**: "I needed to identify the root cause of these transient spikes and implement a fix to stabilize the service."
**Action**: "I started by adding distributed tracing to our request flow to isolate the slow component. The traces revealed that the bottleneck was our caching layer, not the database. I dug into the Redis metrics and noticed high eviction rates. I realized our cache keys were inefficiently designed, causing 'hot keys' and memory churn. I redesigned the key structure to distribute the load evenly and implemented a jittered TTL to prevent cache stampedes."
**Result**: "The latency spikes completely disappeared. P99 latency dropped by 300ms, and we haven't had a timeout issue related to the cache since. I also documented the new caching strategy for the broader engineering team."

## Follow-Up Questions
* "What was the most challenging technical hurdle in solving that problem?"
* "Tell me about a time you tried to solve a problem and your first solution failed."
* "How do you decide when to stop optimizing and consider a problem 'solved'?"

## Hiring Manager Notes
I'm looking for the *methodology*. A strong candidate will walk me through their hypothesis generation, how they gathered data to validate or invalidate those hypotheses, and the systematic steps they took to arrive at the final solution.

## Scoring Rubric

| Rating | Description |
| :--- | :--- |
| **1 - Poor** | Gives up easily, guesses without data, or cannot explain their reasoning. |
| **2 - Fair** | Solves the problem but uses a trial-and-error approach rather than a structured one. |
| **3 - Good** | Uses data to investigate, finds the root cause, and implements a solid fix. |
| **4 - Excellent** | Demonstrates advanced diagnostic skills, handles ambiguity well, and shares learnings with the team. |

## Practice Exercise
Select the most complex technical bug you've ever fixed. Write a STAR response detailing the debugging steps you took, the tools you used, and the underlying concept you uncovered.

## AI Roleplay Prompt
```text
Act as a Tech Lead. Ask me: "Tell me about a time you had to solve a complex, ambiguous technical problem." Probe deeply into my debugging process and ask me to justify my technical decisions. Evaluate my analytical skills.
```
