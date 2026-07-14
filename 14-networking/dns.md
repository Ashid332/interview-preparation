# DNS (Domain Name System)

## Overview
The Domain Name System (DNS) is the phonebook of the internet. It translates human-readable domain names (like `www.google.com`) into machine-readable IP addresses (like `142.250.190.46`). It is a critical, highly distributed, and hierarchical system.

## Interview Questions

### Q1: Explain the step-by-step process of a DNS lookup.
**Difficulty:** Medium | **Frequency:** Very High | **Companies:** Amazon, Cloudflare, Google

**Excellent Answer:**
When you type a URL, the system checks caches first (Browser Cache -> OS Cache -> Router Cache -> ISP Resolver Cache). If not found, a recursive lookup occurs:
1. **Recursive Resolver:** The ISP's DNS server takes the query and asks other servers.
2. **Root Name Server:** The resolver asks the Root server, which responds with the IP of the TLD (Top-Level Domain) server for `.com`.
3. **TLD Name Server:** The resolver asks the `.com` TLD server, which responds with the IP of the Authoritative Name Server for `google.com`.
4. **Authoritative Name Server:** The resolver asks the authoritative server, which holds the actual DNS records (e.g., A Record), and returns the IP address.
5. The resolver caches the IP and returns it to the client.

**Common Mistakes:**
- Omitting the various caching layers (caching is why DNS is actually fast).
- Confusing a recursive resolver with an authoritative name server.

## Real-World Applications
- **Global Routing:** Using DNS to route users to the nearest data center (Geo-DNS).
- **Service Discovery:** Using internal DNS in Kubernetes to allow microservices to find each other.

## Practice Problems
| Problem | Difficulty | Focus Area | Link/Description |
|---|---|---|---|
| Types of DNS Records | Easy | Configurations | Explain A, AAAA, CNAME, and MX records |
| DNS as Load Balancer | Medium | System Design | Discuss how Round-Robin DNS works and its flaws |

## Hiring Manager Perspective
"What happens when you type google.com?" is the most famous interview question, and DNS is step one. Candidates who can confidently explain the recursive hierarchy and the importance of TTL (Time To Live) in caching immediately establish credibility.

## AI Interview Coach
**ChatGPT/Claude Prompt:**
```text
Act as a systems interviewer. Ask me to walk through a full DNS resolution process. Challenge me on what happens when a DNS record is updated but users are still seeing the old IP address.
```
