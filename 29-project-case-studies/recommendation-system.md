# Recommendation System Case Study

## Problem
Users on a media platform (like Netflix or YouTube) face choice paralysis. We need a system that suggests personalized content to increase user engagement and watch time.

## Requirements
* **Functional:**
  * Display a personalized feed of recommended items.
  * Capture user interactions (clicks, watch time, likes).
  * Update recommendations based on recent activity.
* **Non-Functional:**
  * Low latency for generating the feed (under 200ms).
  * Ability to ingest massive amounts of telemetry data in real-time.
  * System must handle "cold starts" for new users or new content.

## Architecture
1. **Telemetry Collector:** API that receives user interaction events.
2. **Data Streaming:** Kafka ingests the high-throughput interaction data.
3. **Batch Processing (Hadoop/Spark):** Nightly jobs that train complex machine learning models (Collaborative Filtering, Deep Learning) on historical data to generate user profiles and item similarities.
4. **Stream Processing (Flink/Spark Streaming):** Processes real-time events from Kafka to update short-term user preferences (e.g., the user is watching action movies *right now*).
5. **Serving Layer:** An API that fetches pre-computed recommendations from a fast key-value store and applies lightweight, real-time re-ranking based on context (time of day, device type).
6. **Storage:** HDFS/S3 for raw data lake, Redis/Cassandra for serving recommendations.

## Trade-offs
* **Pre-computation vs Real-time calculation:** Calculating recommendations on the fly is too slow for complex models. We pre-compute the heavy lifting in batch jobs and store the results in Redis. The trade-off is that recommendations might be a few hours out of date, which we mitigate by adding a lightweight real-time re-ranking layer.
* **Exploration vs Exploitation:** Showing only things the user likes (exploitation) leads to filter bubbles. Showing random things (exploration) risks disengagement. We tune the algorithm to inject a small percentage of novel content to learn new preferences.

## Scaling Decisions
* **Data Lake:** Moved from a relational data warehouse to a Data Lake architecture (S3 + Parquet files) to affordably store petabytes of unstructured interaction logs.
* **Separation of Concerns:** Separated the model training infrastructure (GPU clusters, batch processing) from the serving infrastructure (high-CPU APIs, Redis) because their resource needs and scaling triggers are entirely different.

## Technology Choices
* **Data Ingestion:** Apache Kafka.
* **Processing:** Apache Spark (Batch) and Apache Flink (Stream).
* **Storage:** AWS S3 (Data Lake), Cassandra/Redis (Serving).
* **ML Frameworks:** TensorFlow or PyTorch.

## Common Interview Questions
* How do you solve the "cold start" problem for a brand new user?
* How do you ensure the system doesn't recommend items the user has already consumed?
* How does the data pipeline handle out-of-order or duplicate events?

## Strong Answers
* "For new users (cold start), collaborative filtering fails. We fall back to content-based filtering (recommending items similar to what they are currently viewing) or popularity-based recommendations until we gather enough interaction data."
* "To prevent recommending already consumed items, the serving layer queries a Bloom Filter. The Bloom Filter is highly memory-efficient and quickly checks if an item ID exists in the user's history before adding it to the final feed."

## Weak Answers
* "I'd just query the SQL database for what users with similar demographics liked." *(SQL cannot handle this level of complexity or scale efficiently).*
* "Run the ML model every time the user refreshes the page." *(Guarantees unacceptable latency).*

## Hiring Manager Notes
This tests a candidate's understanding of data engineering and machine learning pipelines. You don't necessarily need to be an ML expert, but you must understand how to move data, train models offline, and serve results online with low latency.

## Possible Follow-up Questions
* How do you A/B test a new recommendation algorithm without hurting overall metrics?
* How would you architect the system to handle a viral video that suddenly gets millions of views?

## System Design Discussion
Clearly differentiate between the "Offline Pipeline" (batch training) and the "Online Pipeline" (real-time serving). Walk the interviewer through how data flows from the user's click, into Kafka, into the data lake, into the model, and back out as a recommendation on the next page load.
