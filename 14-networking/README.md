# Networking Interview Guide

## Overview
Networking is the backbone of all distributed systems. Interviews often test your understanding of how data moves across the internet, the differences between communication protocols, and how to optimize for speed, reliability, and security.

## Interview Questions

### Q1: Why is understanding networking important for a software engineer?
**Difficulty:** Easy | **Frequency:** Medium | **Companies:** Google, Cloudflare, Cisco

**Excellent Answer:**
Software doesn't exist in a vacuum. Applications rely on network calls, which introduce latency, packet loss, and security vulnerabilities. Understanding the OSI model, TCP/UDP, and DNS helps engineers diagnose bottlenecks, design robust APIs, debug connection timeouts, and architect systems that degrade gracefully under poor network conditions.

**Common Mistakes:**
- Dismissing networking as an "IT or DevOps problem."
- Assuming zero latency and infinite bandwidth in distributed system designs.

## Real-World Applications
- **Microservices:** Communicating via gRPC/HTTP over virtual private clouds (VPCs).
- **Streaming:** Using UDP for low-latency video streaming.
- **Security:** Configuring TLS/SSL to encrypt HTTP traffic.

## Practice Problems
| Problem | Difficulty | Focus Area | Link/Description |
|---|---|---|---|
| Trace a Request | Medium | General Networking | What happens when you type google.com? |
| Debugging Latency | Hard | TCP/IP | Diagnose why an API call is taking 5 seconds |

## Hiring Manager Perspective
Even for backend developers, lacking basic networking knowledge is a red flag. If a candidate can't explain the difference between a TCP connection timeout and an HTTP 500 error, they will struggle to debug modern microservices. 

## AI Interview Coach
**ChatGPT/Claude Prompt:**
```text
Act as a technical interviewer. Ask me a broad networking question to assess my baseline knowledge. Evaluate my understanding of latency, bandwidth, and the realities of network communication.
```
