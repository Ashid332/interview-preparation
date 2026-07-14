# System Design Interview Scorecard

This rubric evaluates the candidate's ability to architect large-scale, distributed systems. It focuses on requirement gathering, component design, scalability, bottleneck identification, and trade-off analysis.

## Scoring Rubric

* **5 - Strong Hire:**
  * **Traits:** Drives the entire conversation. Deep expertise in distributed systems.
  * **Evidence:** Asks excellent clarifying questions. Proposes a robust, scalable architecture. Proactively identifies bottlenecks (SPOFs, database hotspots) and offers multiple viable solutions, explicitly weighing trade-offs (e.g., consistency vs. availability).
* **4 - Hire:**
  * **Traits:** Strong, capable design. Needs only minor course correction.
  * **Evidence:** Gathers requirements well. Draws a logical architecture. Understands standard scaling techniques (caching, load balancing, sharding). Can discuss trade-offs when prompted.
* **3 - Neutral:**
  * **Traits:** Designs a basic system but struggles with scale. Needs heavy guidance.
  * **Evidence:** Misses key non-functional requirements (e.g., latency limits). Architecture is monolithic or lacks basic scaling components. Hand-waves over hard problems (e.g., "we'll just put a cache here" without explaining invalidation).
* **2 - Lean No Hire:**
  * **Traits:** Cannot design a functional system for the given constraints.
  * **Evidence:** Jumps straight to naming specific technologies (e.g., "I'll use Kafka and Cassandra") without explaining *why*. Fails to understand basic concepts like databases vs. caches or synchronous vs. asynchronous processing.
* **1 - Strong No Hire:**
  * **Traits:** Completely lost. Refuses to adapt design when obvious flaws are pointed out.
  * **Evidence:** No understanding of client-server architecture. Cannot draw a basic diagram. Combative when asked to explain their reasoning.

## Hiring Manager Notes

For the Hiring Committee:
- System design expectations scale heavily with seniority. A "3" is perfectly fine for a Junior engineer (who might just design a basic CRUD app), but a "3" is a clear No Hire for a Senior or Staff engineer.
- Look for the "trade-off" signal. Candidates who claim their system is "perfect and has no downsides" lack practical experience. A 5/Strong Hire candidate will happily tear apart their own design to show its limits.
