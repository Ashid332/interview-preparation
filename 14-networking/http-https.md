# HTTP and HTTPS

## Overview
Hypertext Transfer Protocol (HTTP) is the application-level protocol that powers the World Wide Web. HTTPS is the secure version, using TLS/SSL to encrypt communications, ensuring privacy, data integrity, and authentication.

## Interview Questions

### Q1: What happens during an HTTPS/TLS Handshake?
**Difficulty:** Hard | **Frequency:** High | **Companies:** Cloudflare, Stripe, Meta

**Excellent Answer:**
The TLS handshake occurs *after* the TCP 3-way handshake.
1. **ClientHello:** The client sends supported cipher suites and a random byte string.
2. **ServerHello:** The server selects a cipher suite, sends its digital certificate (containing its public key), and a server random byte string.
3. **Authentication:** The client verifies the certificate against its trusted Certificate Authorities (CAs).
4. **Key Exchange:** The client encrypts a "pre-master secret" using the server's public key and sends it.
5. **Session Keys:** Both generate symmetric session keys from the pre-master secret and random strings.
6. **Finished:** Both send encrypted "Finished" messages. Secure symmetric encryption begins.

**Common Mistakes:**
- Confusing asymmetric (public/private key) encryption with symmetric encryption. Asymmetric is used for the handshake; symmetric is used for the actual data transfer because it is much faster.
- Forgetting the role of Certificate Authorities.

## Real-World Applications
- **E-commerce:** Securing credit card transactions and personal data.
- **APIs:** All modern REST or GraphQL APIs should be served over HTTPS to prevent man-in-the-middle attacks.

## Practice Problems
| Problem | Difficulty | Focus Area | Link/Description |
|---|---|---|---|
| HTTP/1.1 vs HTTP/2 | Medium | Performance | Discuss multiplexing and server push |
| API Security | Medium | HTTPS | Explain how to secure a public-facing API |

## Hiring Manager Perspective
Understanding HTTPS shows a candidate cares about security. I look for the realization that asymmetric encryption is computationally expensive, which is why the handshake establishes a symmetric key for the bulk of the communication.

## AI Interview Coach
**ChatGPT/Claude Prompt:**
```text
Act as a security-focused engineering interviewer. Ask me to detail the steps of a TLS handshake and explain why we don't just use asymmetric encryption for the entire connection.
```
