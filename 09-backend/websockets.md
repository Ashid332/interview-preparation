# WebSockets Interview Guide

## Overview
WebSockets provide a full-duplex communication channel over a single, long-lived TCP connection. Unlike HTTP, where the client must always initiate the request, WebSockets allow the server to push data to the client in real-time.

## Interview Questions

### Q1: How does a WebSocket connection start?
**Difficulty:** Medium | **Frequency:** High | **Companies:** Slack, Discord, Binance
**Excellent Answer:**
A WebSocket connection begins with a standard HTTP GET request from the client, which includes an `Upgrade: websocket` header. If the server supports WebSockets, it responds with an `HTTP 101 Switching Protocols` status code. At this point, the HTTP protocol is abandoned, and the TCP connection is kept open to be used for the bidirectional WebSocket protocol.
**Common Mistakes:**
- Not knowing that it starts as an HTTP request.

### Q2: How do you scale WebSocket connections horizontally?
**Difficulty:** Hard | **Frequency:** High | **Companies:** WhatsApp, Twitch
**Excellent Answer:**
Scaling WebSockets is challenging because they are stateful, long-lived connections. You cannot simply round-robin requests. To scale horizontally, you need a pub/sub mechanism (like Redis Pub/Sub or Kafka) connecting the backend servers. When Server A receives a message intended for a user connected to Server B, it publishes the message to Redis, Server B consumes it, and pushes it down its open WebSocket to the user. Load balancers must also be configured to allow long-lived connections.

## Real-World Applications
- Real-time chat applications.
- Live sports scores and stock tickers.
- Collaborative editing (e.g., Google Docs).
- Multiplayer online games.

## Practice Problems

| Problem | Description | Difficulty |
|---------|-------------|------------|
| Handshake | Explain the HTTP headers required for a WebSocket upgrade. | Easy |
| State Management | Design a system to track "online/offline" status for millions of users. | Hard |

## Hiring Manager Perspective
"WebSockets change the architecture from stateless to stateful. I look for engineers who understand the challenges of memory management, connection drops, heartbeats (ping/pong), and horizontal scaling in a stateful environment."

## AI Interview Coach
**Prompt:**
> "Act as a System Design interviewer. Ask me how I would build a scalable live-chat architecture using WebSockets, including load balancing and server-to-server communication."
