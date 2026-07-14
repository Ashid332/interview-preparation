# Cloud Engineering & Architecture

## Overview
Cloud computing is the delivery of computing servicesâ€”including servers, storage, databases, networking, software, and analyticsâ€”over the Internet. This section covers overarching cloud architecture concepts as well as deep dives into the major providers (AWS, Azure, GCP).

## Interview Questions

### Question 1: Describe the Shared Responsibility Model in cloud computing.
* **Difficulty:** Easy
* **Frequency:** High
* **Companies:** AWS, Microsoft, Google

**Excellent Answer:**
The Shared Responsibility Model outlines that security and compliance are a shared effort between the cloud provider and the customer. The provider is generally responsible for "Security OF the Cloud" (physical hardware, virtualization layers, global infrastructure). The customer is responsible for "Security IN the Cloud" (customer data, IAM, OS patching for IaaS, network configurations).

**Common Mistakes:**
- Believing the cloud provider is responsible for customer data backups and application-level security.
- Failing to distinguish how the model shifts between IaaS, PaaS, and SaaS.

## Real-World Applications
Cloud computing enables global reach, high availability, and disaster recovery. Architectures are designed to be fault-tolerant, deploying resources across multiple Availability Zones or Regions.

## Practice Problems
| Problem | Description | Complexity | Link |
| --- | --- | --- | --- |

## Hiring Manager Perspective
Hiring managers want architects who design for failure. They prioritize candidates who understand cost optimization (FinOps), security baselines, and how to choose the right service (e.g., IaaS vs PaaS vs Serverless) based on business requirements.

## AI Interview Coach
**ChatGPT/Claude/Gemini Prompt:**
> "Act as a Principal Cloud Architect. Ask me 3 questions about evaluating trade-offs when migrating a legacy on-premise monolithic application to a cloud-native architecture."
