# System Design Problem: Chat System

## Overview
Designing a chat system (like WhatsApp, Discord, or Slack) tests your knowledge of real-time bidirectional communication, managing stateful connections, message ordering, and high-throughput data delivery.

## Interview Questions

### Q1: How do you handle real-time message delivery to clients?
**Difficulty:** Hard | **Frequency:** High | **Companies:** Meta, Discord, Slack

**Excellent Answer:**
To deliver messages in real-time, we use persistent connections:
1. **WebSockets:** The primary protocol for bidirectional, persistent communication between client and server.
2. **Connection Management:** Use a fleet of stateful "Connection Servers" to hold WebSocket connections.
3. **Routing:** When User A sends a message to User B, the request hits an API server, saves to the database, and publishes to a message queue/PubSub system (e.g., Redis Pub/Sub). The specific Connection Server holding User B's WebSocket subscribes to this channel and pushes the message to User B.
4. **Fallback:** Long polling can be used as a fallback if WebSockets are unavailable.

**Common Mistakes:**
- Using basic HTTP polling (which causes massive server load and latency).
- Storing WebSocket connections in a stateless API tier (connections are inherently stateful).
- Not addressing message ordering or handling offline users.

## Real-World Applications
- **WhatsApp/Telegram:** 1-to-1 and group messaging with offline sync.
- **Discord:** Large-scale group chat with presence indicators (online/offline status).
- **Customer Support Chat:** Live chat widgets on websites.

## Practice Problems
| Problem | Difficulty | Focus Area | Link/Description |
|---|---|---|---|
| Group Chat Scale-out | Hard | Fan-out | Design a chat system for groups of 100,000+ users |
| Presence Service | Medium | Heartbeats, Caching | Build a system to track user online/offline status |

## Hiring Manager Perspective
Chat systems separate senior candidates from mid-level ones. Managing state in a distributed system is hard. I look for a deep understanding of push vs. pull mechanisms, how to scale stateful WebSocket servers, and how to gracefully handle network drops and retries.

## AI Interview Coach
**ChatGPT/Claude Prompt:**
```text
Act as a senior engineering interviewer. Ask me to design a 1-to-1 real-time chat application. Push me specifically on how I would architect the connection management tier and how I would ensure message ordering.
```
