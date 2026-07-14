# Software Security

## Overview
Software security is the practice of designing, building, and testing software to ensure it is protected against malicious attacks and vulnerabilities. In an era of constant cyber threats and strict data privacy regulations, engineering interviews increasingly focus on a candidate's ability to build secure systems by design. This involves understanding core principles like authentication, authorization, encryption, and common web vulnerabilities.

## Interview Questions

### Question 1: What is "Defense in Depth"?
* **Difficulty:** Medium
* **Frequency:** High
* **Companies:** Microsoft, Amazon, Cloudflare

**Excellent Answer:**
Defense in Depth is a security principle that involves layering multiple security controls and defenses throughout an IT system. The idea is that if one layer fails or is bypassed, a subsequent layer will catch the threat. For example, in a web application, you don't just rely on a firewall. You also implement secure coding practices (to prevent XSS/SQLi), use strong authentication (MFA), enforce principle of least privilege in the database, and encrypt data at rest. It assumes that breaches will happen and aims to limit the blast radius.

**Common Mistakes:**
* Believing a single strong perimeter defense (like a WAF) is sufficient.
* Confusing defense in depth with "security through obscurity."

## Real-World Applications
* **Compliance:** Meeting regulatory standards like GDPR, HIPAA, or PCI-DSS requires stringent implementation of security best practices.
* **Incident Response:** Designing systems with robust audit logging to allow security teams to trace and remediate breaches quickly.

## Practice Problems

| Problem | Type | Focus | Difficulty |
| :--- | :--- | :--- | :--- |
| Design a secure file upload service | System Design | Malware scanning, permissions | Medium |
| Audit a codebase for common security flaws | Practical | Code review, OWASP | Medium |

## Hiring Manager Perspective
Hiring managers want to see a security-first mindset. They aren't always looking for security experts (unless it's a specialized role), but they expect software engineers to be aware of the OWASP Top 10, to understand how to handle sensitive user data responsibly, and to think like an attacker when designing a system.

## AI Interview Coach
**Prompt for ChatGPT/Claude/Gemini:**
> "Act as a security-focused interviewer. Ask me three introductory questions about secure software development lifecycles (SDLC) and general security principles. Provide feedback on my awareness of modern security threats."
