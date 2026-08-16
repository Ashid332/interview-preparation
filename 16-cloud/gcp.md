# Google Cloud Platform (GCP)

## Overview
Google Cloud Platform is known for its high-performance global network, deep expertise in data analytics, and machine learning capabilities. It is the birthplace of Kubernetes and offers highly developer-friendly serverless and container offerings.

## Interview Questions

### Question 1: How does BigQuery achieve its high performance for data analytics?
* **Difficulty:** Medium
* **Frequency:** High
* **Companies:** Google, Spotify, Twitter

**Excellent Answer:**
BigQuery is a fully-managed, serverless data warehouse. It achieves massive scale and speed through a combination of columnar storage (Capacitor) and a distributed, massively parallel processing (MPP) architecture (Dremel). When a query is run, Dremel creates a highly scalable execution tree that distributes the query across thousands of machines to scan petabytes of data in seconds, and utilizes Google's high-speed Jupiter network to shuffle data rapidly.

**Common Mistakes:**
- Describing BigQuery as a traditional relational database rather than an OLAP data warehouse.
- Forgetting to mention the separation of compute and storage, which is key to its serverless nature.

## Real-World Applications
GCP excels in big data processing pipelines (Dataflow/PubSub), globally scalable databases (Cloud Spanner), and container orchestration (GKE).

## Practice Problems
| Problem | Description | Complexity | Link |
| --- | --- | --- | --- |

## Hiring Manager Perspective
GCP interviewers emphasize knowledge of data engineering principles and containerization. Because GCP's network is fundamentally global, a strong understanding of how global load balancers and VPCs work in GCP compared to other clouds is highly valued.

## AI Interview Coach
**ChatGPT/Claude/Gemini Prompt:**
> "Act as a Google Cloud Interviewer. Ask me scenario-based questions on choosing between Cloud Run, App Engine, and Google Kubernetes Engine (GKE) for a new microservices project."
