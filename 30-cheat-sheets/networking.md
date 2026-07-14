# Networking Cheat Sheet

## Key Concepts
| Concept | Description |
|---|---|
| OSI Model | 7 layers of networking (Physical, Data Link, Network, Transport, Session, Presentation, Application). |
| TCP/IP | Core protocols of the Internet. TCP is reliable/connection-oriented; UDP is fast/connectionless. |
| DNS | Domain Name System - translates human-readable domain names to IP addresses. |
| HTTP/HTTPS | Hypertext Transfer Protocol. HTTPS adds TLS/SSL for encryption. |

## Must-Know Items
- 3-way handshake in TCP (SYN, SYN-ACK, ACK).
- Differences between HTTP/1.1, HTTP/2 (multiplexing), and HTTP/3 (QUIC/UDP).
- What happens when you type a URL into a browser.
- REST vs GraphQL vs gRPC.

## Common Interview Questions (Quick)
1. What happens when you type google.com into your browser?
2. Explain the difference between TCP and UDP. Give use cases for both.
3. How does DNS resolution work?
4. What is a reverse proxy?

## Critical Commands/Patterns
```bash
# Debugging tools
ping google.com      # Check ICMP connectivity
traceroute google.com # Path packets take to host
curl -v https://api.com # Verbose HTTP request
netstat -tulpn        # List open ports
```

## Decision Framework
- **TCP vs UDP:** Use TCP for file transfer, web browsing, emails (reliability matters). Use UDP for video streaming, gaming, VoIP (speed matters, dropped packets are acceptable).
- **REST vs gRPC:** Use REST for public-facing CRUD APIs. Use gRPC for high-performance internal microservice communication.

## Common Mistakes
- Confusing a Forward Proxy (protects clients, bypasses restrictions) with a Reverse Proxy (protects servers, load balances).
- Not understanding CORS (Cross-Origin Resource Sharing) and why preflight (`OPTIONS`) requests happen.

## One-Minute Review
- Networking is about layers. Understand how data moves from Application (HTTP) to Transport (TCP/UDP) to Network (IP). "What happens when you type a URL" is the ultimate test of full-stack networking knowledge.
