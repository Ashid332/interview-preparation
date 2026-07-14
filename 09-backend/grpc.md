# gRPC Interview Guide

## Overview
gRPC (gRPC Remote Procedure Calls) is an open-source, high-performance RPC framework developed by Google. It uses HTTP/2 for transport and Protocol Buffers (Protobuf) as its interface description language. It is designed to connect services in and across data centers with pluggable support for load balancing, tracing, health checking, and authentication.

## Interview Questions

### Q1: What are the main advantages of gRPC over REST?
**Difficulty:** Medium | **Frequency:** High | **Companies:** Google, Uber, Netflix
**Excellent Answer:**
1. **Performance:** gRPC uses HTTP/2, which supports multiplexing, header compression, and binary framing.
2. **Payload:** It uses Protocol Buffers, a binary format that is much smaller and faster to serialize/deserialize than JSON.
3. **Strict Contracts:** The `.proto` file serves as a strongly-typed contract between client and server, enabling auto-generation of client/server code in multiple languages.
4. **Streaming:** Built-in support for unary, client-streaming, server-streaming, and bidirectional streaming.
**Common Mistakes:**
- Saying it can completely replace REST for front-end clients (browser support for gRPC is still complex and requires proxies like gRPC-Web).

### Q2: Explain the different streaming types in gRPC.
**Difficulty:** Medium | **Frequency:** Medium | **Companies:** Dropbox, Lyft
**Excellent Answer:**
- **Unary:** Standard request/response (client sends one request, gets one response).
- **Server Streaming:** Client sends one request, server responds with a stream of messages.
- **Client Streaming:** Client sends a stream of messages, server responds with one message.
- **Bidirectional Streaming:** Both client and server send a sequence of messages independently.

## Real-World Applications
- Microservice-to-microservice communication.
- Low-latency, high-throughput systems.
- IoT device communication.

## Practice Problems

| Problem | Description | Difficulty |
|---------|-------------|------------|
| Protobuf | Write a `.proto` file defining a User service with nested message types. | Easy |
| Versioning | Explain how to safely add or remove fields in a Protobuf message without breaking clients. | Medium |

## Hiring Manager Perspective
"gRPC is the backbone of modern microservices. I evaluate candidates on their understanding of backwards compatibility in Protobuf, why HTTP/2 matters, and when to use streaming versus standard unary calls."

## AI Interview Coach
**Prompt:**
> "Act as a backend infrastructure interviewer. Ask me about gRPC vs REST, the benefits of Protobuf, and how HTTP/2 improves RPC performance."
