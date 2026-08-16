# Docker

## Overview
Docker is a platform designed to help developers build, share, and run modern applications. It packages software into standardized units called containers that have everything the software needs to run including libraries, system tools, code, and runtime.

## Interview Questions

### Question 1: Explain the difference between a virtual machine and a Docker container.
* **Difficulty:** Easy
* **Frequency:** Very High
* **Companies:** IBM, Google, Microsoft

**Excellent Answer:**
A Virtual Machine (VM) includes the application, the necessary binaries and libraries, and an entire guest operating system, all of which may be tens of GBs in size. In contrast, Docker containers share the host system's kernel and isolate the application processes from the rest of the system. This makes containers incredibly lightweight, fast to start, and less resource-intensive compared to VMs. 

**Common Mistakes:**
- Stating that Docker is faster without explaining that it's due to skipping OS boot sequences and sharing the host kernel.
- Assuming containers offer the exact same security isolation as full VMs (VMs have stronger hardware-level isolation).

## Real-World Applications
Docker is used heavily for ensuring consistency across multiple environments (Dev, Test, Prod), facilitating microservices architectures, local development environments, and CI/CD automated testing.

## Practice Problems
| Problem | Description | Complexity | Link |
| --- | --- | --- | --- |

## Hiring Manager Perspective
Managers want to know that you understand container lifecycle, image optimization, and security best practices (like running as non-root). Knowing how to write a good Dockerfile is an absolute baseline.

## AI Interview Coach
**ChatGPT/Claude/Gemini Prompt:**
> "Act as a Senior DevOps Engineer. Present me with a poorly written Dockerfile and ask me to identify the anti-patterns and optimize it for size, caching, and security."
