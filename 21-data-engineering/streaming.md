# Stream Processing & Real-time Data

## Overview
Stream processing deals with continuous streams of data, processing them in real-time or near real-time. Technologies like Apache Kafka, Flink, and Spark Streaming are central to this domain.

## Interview Questions
**Question:** In Apache Kafka, what is a consumer group and how does it relate to topic partitions?
- **Difficulty/Frequency/Companies:** Medium / High / LinkedIn, Uber, Confluent
- **Excellent Answer:** A consumer group is a set of consumers cooperating to consume data from a topic. Kafka assigns each partition in the topic to exactly one consumer within the group. This allows for parallel processing. If you have more consumers than partitions, the extra consumers will sit idle.
- **Common Mistakes:** Thinking multiple consumers in the same group can read from the same partition, leading to duplicate processing.

## Real-World Applications
- **Fraud Detection:** Analyzing credit card transactions in milliseconds to block fraudulent charges.
- **Real-time Analytics:** Updating live dashboards for live events or social media trending topics.

## Practice Problems

| Problem Name | Type | Difficulty | Focus Area |
| --- | --- | --- | --- |
| Exactly-Once Semantics | Architecture | Hard | Kafka/Flink Guarantees |
| Handling Out-of-Order Events | Concept | Hard | Watermarks/Windowing |
| Design Real-time Leaderboard | System Design | Medium | Stream Aggregation |

## Hiring Manager Perspective
Streaming is significantly harder than batch processing. I test candidates on their understanding of state management, late-arriving data, windowing functions, and delivery guarantees (at-least-once vs. exactly-once).

## AI Interview Coach Prompts
- **ChatGPT:** "Test my knowledge on event-time vs. processing-time in stream processing frameworks like Apache Flink."
- **Claude:** "Ask me an interview question about how to design a real-time fraud detection pipeline. Focus on handling late events and state."
- **Gemini:** "Simulate a deep-dive interview on Apache Kafka internals, focusing on replication, partitions, and offset management."
