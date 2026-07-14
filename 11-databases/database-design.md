# Database Design & Modeling

## Overview
Database design involves structuring a database to reduce redundancy and ensure data integrity. It encompasses entity-relationship modeling, normalization in RDBMS, and query-driven design in NoSQL.

## Interview Questions
**Question:** What is database normalization, and when might you intentionally denormalize?
- **Difficulty/Frequency/Companies:** Medium / Very High / Meta, Google, Microsoft
- **Excellent Answer:** Normalization organizes data to reduce redundancy and improve data integrity (e.g., 1NF, 2NF, 3NF). Denormalization intentionally introduces redundancy to improve read performance by avoiding expensive joins. It's often used in read-heavy applications like data warehouses or high-traffic web apps.
- **Common Mistakes:** Defining normalization correctly but failing to provide a realistic scenario where denormalization is preferred (like a timeline or news feed).

## Real-World Applications
- **Social Networks:** Denormalizing user profiles into posts to serve feeds quickly without massive joins.
- **Banking:** Strict 3NF normalized design to ensure absolutely no data anomalies during updates.

## Practice Problems

| Problem Name | Type | Difficulty | Focus Area |
| --- | --- | --- | --- |
| Design Uber's Database | System Design | Hard | Spatial Data, Scale |
| Normalized vs Denormalized Schema | Modeling | Medium | Trade-offs |
| Schema Evolution Strategy | Architecture | Hard | Zero-downtime migrations |

## Hiring Manager Perspective
I assess if a candidate can translate business requirements into an efficient schema. They need to understand read vs. write ratios and how those dictate normalization choices.

## AI Interview Coach Prompts
- **ChatGPT:** "Provide a complex business scenario (like a ride-sharing app) and ask me to design the relational schema. Critique my normalization."
- **Claude:** "Ask me to redesign a highly normalized schema into a NoSQL structure suitable for a high-read-throughput environment."
- **Gemini:** "Roleplay an interview focusing on zero-downtime database schema migrations for a massive production table."
