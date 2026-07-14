# Amazon Web Services (AWS)

## Overview
AWS is the world's most comprehensive and broadly adopted cloud platform, offering over 200 fully featured services from data centers globally. It is widely used from startups to the largest enterprises.

## Interview Questions

### Question 1: Explain the difference between an Application Load Balancer (ALB) and a Network Load Balancer (NLB).
* **Difficulty:** Medium
* **Frequency:** Very High
* **Companies:** Amazon, Netflix, Capital One

**Excellent Answer:**
An ALB operates at Layer 7 (Application layer) of the OSI model. It is ideal for routing HTTP/HTTPS traffic, supports path-based and host-based routing, and can inspect headers. An NLB operates at Layer 4 (Transport layer). It routes TCP/UDP traffic and is capable of handling millions of requests per second while maintaining ultra-low latencies. Use ALB for complex web applications and NLB for extreme performance and static IP requirements.

**Common Mistakes:**
- Not knowing which OSI layer each load balancer operates at.
- Recommending ALB for protocols other than HTTP/HTTPS.

## Real-World Applications
AWS is used to build serverless backends (API Gateway + Lambda), host resilient data stores (DynamoDB, RDS), and manage massive object storage lakes (S3).

## Practice Problems
| Problem | Description | Complexity | Link |
| --- | --- | --- | --- |

## Hiring Manager Perspective
In AWS interviews, depth in core services (EC2, S3, IAM, VPC) is non-negotiable. Managers look for strong security fundamentals (least privilege IAM) and a good grasp of the AWS Well-Architected Framework.

## AI Interview Coach
**ChatGPT/Claude/Gemini Prompt:**
> "Act as an AWS Solutions Architect interviewer. Present me with a scenario where an application is experiencing high database latency on Amazon RDS. Ask me how I would troubleshoot and resolve it."
