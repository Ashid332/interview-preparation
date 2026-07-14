# OSI Model

## Overview
The Open Systems Interconnection (OSI) model is a conceptual framework that standardizes the functions of a telecommunication or computing system into seven logical layers. Understanding these layers helps isolate network issues and explains how data travels from an application to a physical wire.

## Interview Questions

### Q1: What are the 7 layers of the OSI model? Can you explain how data encapsulates as it moves down the layers?
**Difficulty:** Medium | **Frequency:** Medium | **Companies:** Cisco, Amazon, Akamai

**Excellent Answer:**
The layers from top to bottom are:
7. **Application:** End-user layer (HTTP, FTP, SMTP).
6. **Presentation:** Data formatting and encryption (SSL/TLS, JPEG).
5. **Session:** Maintains connections and sessions (Sockets).
4. **Transport:** Reliable/unreliable delivery, port numbers (TCP, UDP).
3. **Network:** IP addressing and routing (IP, ICMP).
2. **Data Link:** MAC addressing and switches (Ethernet).
1. **Physical:** Physical medium, cables, radio waves (Bits).

**Encapsulation:** As data moves from Layer 7 down to Layer 1, each layer adds its own header (and sometimes a trailer). For example, a web request (L7) gets wrapped in a TCP segment (L4), which is placed in an IP packet (L3), which is placed in an Ethernet frame (L2) before being converted to bits on the wire.

**Common Mistakes:**
- Confusing the Network layer (IP addresses/routers) with the Data Link layer (MAC addresses/switches).
- Failing to explain the concept of encapsulation.

## Real-World Applications
- **Troubleshooting:** "Is it a Layer 3 issue?" means checking if IP routing is working (e.g., using `ping`).
- **Load Balancing:** Layer 4 load balancers route based on IP/Port, while Layer 7 load balancers route based on HTTP headers/URL paths.

## Practice Problems
| Problem | Difficulty | Focus Area | Link/Description |
|---|---|---|---|
| L4 vs L7 Load Balancing | Medium | Load Balancing | Compare the pros/cons of routing at L4 vs L7 |
| Packet Tracing | Hard | Debugging | Identify which OSI layer a specific network error belongs to |

## Hiring Manager Perspective
While reciting the 7 layers is memorization, I look for candidates who can map real-world tools to the layers. If they know that Wireshark reads Layer 2 frames, or that Nginx is a Layer 7 proxy, it shows practical application of theoretical knowledge.

## AI Interview Coach
**ChatGPT/Claude Prompt:**
```text
Act as a network engineer testing a junior colleague. Ask me to troubleshoot a hypothetical network outage by using the OSI model to isolate the problem layer by layer.
```
