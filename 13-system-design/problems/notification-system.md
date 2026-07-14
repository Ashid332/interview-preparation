# System Design Problem: Notification System

## Overview
A notification system delivers alerts (Push, SMS, Email) to users. It involves handling third-party integrations, managing user preferences, dealing with message delivery failures, and scaling to millions of notifications per day.

## Interview Questions

### Q1: How do you ensure that a notification is not sent multiple times, and how do you handle failures from third-party services (like APNs or SendGrid)?
**Difficulty:** Medium | **Frequency:** Medium | **Companies:** Netflix, Uber, Airbnb

**Excellent Answer:**
To prevent duplicate processing, we need idempotency and transactional guarantees:
1. **Deduplication:** Store a unique `notification_id` or `event_id` in a database or cache. Before sending, check if it has already been processed.
2. **Message Queues:** Use a durable queue (like Kafka or RabbitMQ). Workers read from the queue, attempt to send via the 3rd-party provider, and only acknowledge (ACK) the message if successful.
3. **Retry Mechanism:** If a 3rd-party API fails (e.g., rate-limited or 500 error), the worker does not ACK. The message is pushed to a Dead Letter Queue (DLQ) or a retry queue with exponential backoff to prevent overwhelming the provider.

**Common Mistakes:**
- Sending notifications synchronously during an API request.
- Assuming third-party services are always available and fast.
- Not designing for user opt-outs and notification preferences (resulting in spamming users).

## Real-World Applications
- **E-commerce:** Order shipment updates via SMS and Email.
- **Streaming Services:** Push notifications for new episodes (Netflix).
- **Banking:** Fraud alert text messages.

## Practice Problems
| Problem | Difficulty | Focus Area | Link/Description |
|---|---|---|---|
| Priority Queues | Medium | Queue Management | Ensure OTP emails process faster than marketing emails |
| Rate Limiting Outbound | Hard | API Integration | Prevent violating APNs/FCM strict rate limits |

## Hiring Manager Perspective
This question tests practical engineering. Every company has a notification system. I look for robust error handling. Do they mention dead letter queues? Do they consider that Apple/Google push notification services might throttle us? Resilience is the key theme here.

## AI Interview Coach
**ChatGPT/Claude Prompt:**
```text
Act as a system design interviewer. Ask me to architect a notification system that sends 10 million push notifications, emails, and SMS per day. Focus on reliability, retry logic, and integrating with external APIs.
```
