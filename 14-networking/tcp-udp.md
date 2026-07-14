# TCP vs UDP

## Overview
Transmission Control Protocol (TCP) and User Datagram Protocol (UDP) are the two foundational Transport Layer (Layer 4) protocols of the internet. Choosing between them involves trading off reliability and ordering for speed and reduced overhead.

## Interview Questions

### Q1: Compare TCP and UDP. When would you use one over the other?
**Difficulty:** Easy | **Frequency:** Very High | **Companies:** Google, Microsoft, Netflix

**Excellent Answer:**
- **TCP (Transmission Control Protocol):** Connection-oriented. It requires a 3-way handshake before sending data. It guarantees delivery, maintains message order, and handles congestion control. It is reliable but slower.
  - *Use cases:* Web browsing (HTTP/HTTPS), File transfers (FTP), Email (SMTP), SSH.
- **UDP (User Datagram Protocol):** Connectionless. It simply fires packets at a destination without checking if they arrive. There are no guarantees of delivery, ordering, or congestion control. It is fast, lightweight, and allows broadcasting.
  - *Use cases:* Video streaming, VoIP calls, online multiplayer gaming, DNS lookups.

**Common Mistakes:**
- Saying TCP is "better" than UDP. They solve different problems.
- Forgetting that DNS uses UDP (for standard lookups).

## Real-World Applications
- **Video Conferencing (Zoom):** Uses UDP because a dropped frame is better than video pausing to wait for a retransmitted packet (which causes lag).
- **Web Applications:** Use TCP because you cannot have missing chunks in HTML or JSON payloads.

## Practice Problems
| Problem | Difficulty | Focus Area | Link/Description |
|---|---|---|---|
| Implement Reliable UDP | Hard | Protocol Design | Design a reliable protocol on top of UDP (like QUIC) |
| TCP 3-Way Handshake | Medium | Deep Dive | Explain SYN, SYN-ACK, ACK in detail |

## Hiring Manager Perspective
This is a foundational filter question. If a candidate cannot explain why a video game uses UDP and a bank uses TCP, it shows a lack of basic network literacy. I appreciate candidates who mention modern protocols like HTTP/3 (QUIC), which builds reliability on top of UDP to avoid TCP head-of-line blocking.

## AI Interview Coach
**ChatGPT/Claude Prompt:**
```text
Act as a network systems interviewer. Ask me to compare TCP and UDP. Follow up by asking me how HTTP/3 changes the paradigm by utilizing UDP instead of TCP.
```
