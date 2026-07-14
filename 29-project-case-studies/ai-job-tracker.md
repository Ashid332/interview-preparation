# AI Job Tracker Case Study

## Problem
Job seekers struggle to track hundreds of applications across different platforms. The AI Job Tracker allows users to forward job descriptions or emails, automatically parsing the details, updating the application status, and providing tailored resume suggestions.

## Requirements
* **Functional:**
  * Ingest job descriptions via URL scraping or email forwarding.
  * Use AI/LLMs to extract metadata (Company, Role, Salary, Tech Stack).
  * Provide a Kanban board for application tracking.
  * Suggest resume keywords based on the job description.
* **Non-Functional:**
  * Asynchronous processing (AI parsing takes time).
  * High reliability for the data ingestion pipeline.
  * Scalable to handle bursts of data (e.g., a user imports 50 jobs at once).

## Architecture
1. **Client:** Web app with a Kanban interface.
2. **Ingestion API:** Receives URLs or emails.
3. **Message Queue (RabbitMQ/SQS):** Buffers incoming parsing requests.
4. **Worker Nodes:** Consume messages, fetch page content, and call external LLM APIs (e.g., OpenAI).
5. **Database:** PostgreSQL to store users, jobs, statuses, and parsed metadata.
6. **Notification Service:** Alerts the client via WebSockets or SSE when a job has finished parsing.

## Trade-offs
* **Synchronous vs Asynchronous API:** Calling an LLM takes 2-10 seconds. Doing this synchronously blocks the user and risks timeout errors. I chose an asynchronous queue-based architecture, sacrificing immediate feedback for system resilience and better user experience (non-blocking UI).
* **Self-hosted NLP vs Third-party LLM:** Using an API (like OpenAI) is expensive and introduces latency, but provides far superior parsing accuracy for unstructured text compared to a self-hosted, lightweight NER (Named Entity Recognition) model.

## Scaling Decisions
* **Worker Pool Scaling:** The bottleneck is the worker nodes calling the LLM. Implemented auto-scaling on the worker pool based on the length of the message queue.
* **Rate Limiting:** Third-party LLM APIs have rate limits. Implemented a token bucket algorithm in the worker nodes to delay processing and prevent API bans during spikes.

## Technology Choices
* **Backend:** Python (FastAPI) - excellent ecosystem for AI, scraping (BeautifulSoup), and async tasks (Celery).
* **Queue:** RabbitMQ or AWS SQS.
* **Database:** PostgreSQL.
* **Frontend:** React for the dynamic Kanban board.

## Common Interview Questions
* How do you handle failures if the LLM API goes down?
* How do you deal with websites that block web scrapers?
* How is the real-time update sent to the frontend once processing is done?

## Strong Answers
* "If the LLM API fails, the worker catches the exception and negative-acknowledges (NACK) the message in the queue. The queue is configured with a Dead Letter Queue (DLQ) and exponential backoff retry logic, ensuring the parsing request isn't lost but doesn't endlessly drain resources."
* "To update the frontend asynchronously, I used Server-Sent Events (SSE). When the worker finishes writing the parsed data to the database, it triggers an event via Redis Pub/Sub, which the API server picks up and pushes to the client via the open SSE connection."

## Weak Answers
* "I just wait for the OpenAI API to return the data and then send it to the frontend." *(Ignores timeouts, blocking threads, and poor UX).*
* "If it fails, I just tell the user to try again." *(Poor system resilience).*

## Hiring Manager Notes
This project tests a candidate's ability to design asynchronous, event-driven architectures. The integration of external APIs (LLMs) requires careful consideration of latency, rate limits, and failure modes. 

## Possible Follow-up Questions
* How would you store vector embeddings of the job descriptions to match them against a user's resume?
* How do you handle data privacy and user PII when sending data to third-party AI models?

## System Design Discussion
Focus heavily on the background processing pipeline. Draw out the flow from the initial HTTP request, to the queue, to the worker, to the database, and back to the client. Discussing retries, DLQs, and async UI updates will demonstrate seniority.
