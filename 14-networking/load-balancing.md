# Load Balancing

## Overview
Load balancing distributes incoming network traffic across multiple servers. This ensures no single server bears too much demand, improving responsiveness and availability. It is a fundamental concept for scaling any application horizontally.

## Interview Questions

### Q1: What are the differences between Layer 4 and Layer 7 load balancing?
**Difficulty:** Medium | **Frequency:** High | **Companies:** AWS, Meta, Netflix

**Excellent Answer:**
- **Layer 4 (Transport Layer):** Routes traffic based purely on network information like IP addresses and TCP/UDP ports. It doesn't inspect the content of the messages.
  - *Pros:* Extremely fast, low CPU usage.
  - *Cons:* Cannot route based on application state or URLs.
- **Layer 7 (Application Layer):** Routes traffic based on the content of the message, such as HTTP headers, cookies, or URL paths (e.g., routing `/api` to backend A, and `/images` to backend B).
  - *Pros:* Smart routing, supports TLS termination, can handle sticky sessions based on cookies.
  - *Cons:* Slower and more computationally expensive.

**Common Mistakes:**
- Thinking you only need one or the other (large systems use Layer 4 at the edge, and Layer 7 deeper in the architecture).
- Not understanding TLS termination and where certificates live.

## Real-World Applications
- **Nginx/HAProxy:** Common software used for Layer 7 load balancing and reverse proxying.
- **AWS ALB/NLB:** Application Load Balancer (L7) and Network Load Balancer (L4) provided as managed cloud services.

## Practice Problems
| Problem | Difficulty | Focus Area | Link/Description |
|---|---|---|---|
| Consistent Hashing | Hard | Algorithms | Design a load balancer that routes specific users to specific caches |
| Health Checks | Medium | Resilience | Explain how a load balancer knows a backend server is down |

## Hiring Manager Perspective
Load balancers are the front door to your system. I want to know if the candidate understands load balancing algorithms (Round Robin, Least Connections, IP Hash). Strong candidates will also bring up the concept of a "Single Point of Failure" and explain how to make the load balancer itself highly available (e.g., Active-Passive setup with VRRP).

## AI Interview Coach
**ChatGPT/Claude Prompt:**
```text
Act as a cloud architecture interviewer. Ask me to design the load balancing tier for a high-traffic microservices application. Ask me to choose between L4 and L7 balancing and justify my choice based on the workload.
```
