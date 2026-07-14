# Secure Architecture

## Overview
Secure architecture involves designing systems with security integrated from the ground up, rather than bolting it on as an afterthought. This encompasses concepts like threat modeling, network security, encryption at rest and in transit, and designing resilient, fault-tolerant systems that protect sensitive data even when components are compromised.

## Interview Questions

### Question 1: How do you secure data in transit and data at rest?
* **Difficulty:** Easy
* **Frequency:** High
* **Companies:** AWS, Google Cloud, Apple

**Excellent Answer:**
* **Data in Transit:** Secured using Transport Layer Security (TLS/HTTPS). This ensures that data moving over networks cannot be intercepted or tampered with. It requires enforcing HTTPS for all web traffic, using strong cipher suites, and properly managing certificates. For internal microservices communication, mutual TLS (mTLS) is used to verify both the client and the server.
* **Data at Rest:** Secured by encrypting data stored on disks, databases, or object storage (like S3). This is typically done using symmetric encryption (like AES-256) managed via a Key Management Service (KMS). Important fields (like PII) might have application-level encryption before being sent to the database.

**Common Mistakes:**
* Mentioning SSL instead of TLS (SSL is deprecated and insecure).
* Not mentioning Key Management Services (KMS); encrypting data is useless if the encryption key is stored in plain text next to the data.

### Question 2: What is Threat Modeling?
* **Difficulty:** Medium
* **Frequency:** Medium
* **Companies:** Microsoft, Palantir, CrowdStrike

**Excellent Answer:**
Threat modeling is a structured process to identify potential security threats and vulnerabilities in a system architecture, determine the risk they pose, and establish appropriate mitigations. It's ideally done during the design phase. A common methodology is STRIDE, developed by Microsoft, which categorizes threats into: Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, and Elevation of Privilege. By drawing a data flow diagram of the system, we methodically evaluate each boundary and component against these categories.

**Common Mistakes:**
* Viewing threat modeling as an automated scan rather than a design-phase analytical process.
* Focusing only on external hackers and ignoring insider threats or compromised third-party dependencies.

## Real-World Applications
* **VPC Design:** Designing a cloud architecture using Virtual Private Clouds (VPCs) with public subnets for load balancers and private subnets for application servers and databases, restricting direct internet access.
* **Secrets Management:** Migrating hardcoded API keys and database credentials out of code repositories and into secure vaults like HashiCorp Vault or AWS Secrets Manager.

## Practice Problems

| Problem | Type | Focus | Difficulty |
| :--- | :--- | :--- | :--- |
| Design a secure architecture for a healthcare app | System Design | HIPAA, encryption, VPCs | Hard |
| Perform a STRIDE threat model on an IoT device | Architecture | Threat modeling, mitigations | Medium |

## Hiring Manager Perspective
For senior roles and system design interviews, managers look for candidates who proactively address security. They want to see candidates who suggest mTLS for internal service communication, use private subnets for databases, and mention secrets management without being prompted. It demonstrates architectural maturity.

## AI Interview Coach
**Prompt for ChatGPT/Claude/Gemini:**
> "Act as a Staff Security Engineer. Give me a system architecture for a new financial application (including web frontend, API gateway, microservices, and databases). Ask me to perform a threat model on it, identify 3 major security risks, and propose architectural changes to mitigate them."
