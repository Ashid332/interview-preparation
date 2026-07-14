# Chat Application Case Study

## Problem
Users need to send and receive text messages in real-time, either in one-on-one conversations or within group chats, with delivery and read receipts.

## Requirements
* **Functional:**
  * 1-on-1 and group messaging.
  * Real-time delivery.
  * Online status indicators (presence).
  * Message history storage.
* **Non-Functional:**
  * Low latency for real-time feel.
  * High availability.
  * Ability to handle millions of concurrent connections.

## Architecture
1. **Clients:** Connect via WebSockets to chat servers.
2. **Load Balancer:** Routes client connections to available chat servers.
3. **Chat Servers (WebSocket Handlers):** Maintain persistent connections with active clients.
4. **Pub/Sub System (Redis PubSub or Kafka):** Routes messages between different chat servers when users are connected to different nodes.
5. **Presence Servers:** Dedicated services tracking online/offline status using a heartbeat mechanism.
6. **Database:** Fast key-value store (e.g., Cassandra or HBase) for message history.

## Trade-offs
* **WebSockets vs. Long Polling:** WebSockets provide true bi-directional real-time communication but require managing stateful connections on the server. Long polling is stateless but overhead-heavy. Chose WebSockets for low latency.
* **Pushing vs. Pulling Messages for Groups:** For small groups, pushing messages to all users is fine. For massive channels (e.g., Discord/Slack), pushing to 100k users per message is inefficient; clients should pull updates or be batched.

## Scaling Decisions
* **Connection Management:** Managing millions of WebSockets requires tuning OS parameters (open file descriptors) and using efficient async runtimes (e.g., Erlang, Go, or Node.js).
* **Decoupling Services:** Split the API servers (for login, profile updates) from the Chat servers (purely for message routing) to scale them independently.

## Technology Choices
* **Language:** Erlang/Elixir or Go for high concurrency WebSocket management.
* **Message Broker:** Kafka for reliable message ordering and persistence, or Redis Pub/Sub for pure speed.
* **Database:** Cassandra for fast, ordered time-series writes (ideal for chat history).

## Common Interview Questions
* How do you route a message from User A to User B if they are connected to different servers?
* How do you handle temporary network disconnects?
* How is presence (online status) tracked at scale?

## Strong Answers
* "When User A sends a message, Server 1 checks a distributed cache (like Redis) to find which server User B is connected to. If User B is on Server 2, Server 1 publishes the message to a message queue or Pub/Sub channel that Server 2 is subscribed to. Server 2 then pushes it down User B's WebSocket."
* "For presence, I would use a heartbeat mechanism where the client pings the server every 5 seconds. If the server misses three heartbeats, the user is marked offline. To avoid overwhelming the system, status updates are batched and broadcasted via Pub/Sub."

## Weak Answers
* "I'd just save messages to a SQL database and have clients fetch them every second." *(Shows poor understanding of real-time systems and scale).*
* "Keep everything in memory." *(Fails to account for server crashes and message persistence).*

## Hiring Manager Notes
This problem tests a candidate's understanding of stateful vs. stateless services. Managing state (the active connection) is the hardest part of a chat app. Look for candidates who understand Pub/Sub patterns and database choices for time-series data.

## Possible Follow-up Questions
* How would you implement end-to-end encryption?
* How do you sync messages across multiple devices for a single user?

## System Design Discussion
Focus on the data flow. Trace a message from the sender's app, through the load balancer, to the chat server, into the Pub/Sub system, to the receiver's chat server, and finally down to the receiver's app. Clearly articulate how failures are handled at each step.
