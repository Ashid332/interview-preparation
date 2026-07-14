# Cloud Engineer Interview Learning Path

## Role Overview
Cloud Engineers design, deploy, and manage highly available cloud architectures on providers like AWS, GCP, or Azure. This role focuses heavily on cloud-native services, networking, security, and cost optimization. This 10-week path prepares you for Cloud Architect and Cloud Infrastructure roles.

## Prerequisites

| Skill Area | Expected Proficiency Level | Resources for Review |
|------------|----------------------------|----------------------|
| IT Fundamentals | Intermediate (Networking, OS) | Network+ / Linux+ equivalents |
| Scripting | Basic/Intermediate (Python/Bash) | Python scripting basics |
| Cloud Basics | Familiarity with one major provider | AWS Cloud Practitioner / Azure Fundamentals |

## Path Overview

```mermaid
gantt
    title Cloud Engineer 10-Week Preparation Plan
    dateFormat  w
    axisFormat %W
    section Core Infrastructure
    Compute & Network     :a1, 0, 3w
    section Data & Storage
    Databases & Storage   :a2, after a1, 2w
    section Security & Scale
    IAM & Serverless      :a3, after a2, 3w
    section Interview Prep
    System Design & Mocks :a4, after a3, 2w
```

## Weekly Roadmap

### Weeks 1-3: Core Compute & Networking
Building the foundational blocks of cloud environments.

| Week | Focus Area | Key Concepts | Practice Goal |
|------|------------|--------------|---------------|
| 1 | Compute Services | VMs (EC2/GCE), Autoscaling Groups, Load Balancers | Deploy a load-balanced web server cluster |
| 2 | VPC & Networking | Subnets, Route Tables, NAT Gateways, Peering | Design and implement a public/private VPC architecture |
| 3 | Hybrid Cloud & CDN | VPNs, Direct Connect, CloudFront, Route53 | Configure a static website behind a CDN with custom DNS |

### Weeks 4-5: Storage & Databases
Managing data securely and cost-effectively.

| Week | Focus Area | Key Concepts | Practice Goal |
|------|------------|--------------|---------------|
| 4 | Object & Block Storage | S3/GCS, EBS, EFS, Storage Tiers, Lifecycle Policies | Automate backups of an EBS volume using snapshots |
| 5 | Managed Databases | RDS, DynamoDB, Aurora, Read Replicas, Multi-AZ | Deploy a highly available RDS instance and test failover |

### Weeks 6-8: Security, Serverless & IaC
Securing the perimeter and modernizing architectures.

| Week | Focus Area | Key Concepts | Action Item |
|------|------------|--------------|-------------|
| 6 | IAM & Security | Roles, Policies, Principle of Least Privilege, KMS | Implement strict IAM roles for an application EC2 instance |
| 7 | Serverless Architectures | Lambda, API Gateway, SQS/SNS, Event-Driven | Build a serverless image processing pipeline |
| 8 | Infrastructure as Code | CloudFormation / Terraform state | Migrate manual AWS configurations to Terraform |

### Weeks 9-10: Cloud System Design & Behavioral
Preparing for architecture whiteboard rounds.

| Week | Focus Area | Key Concepts | Action Item |
|------|------------|--------------|-------------|
| 9 | Well-Architected Framework| Security, Reliability, Performance, Cost Optimization | Audit a sample architecture against the 5 pillars |
| 10 | Mock Interviews | Whiteboarding cloud migrations, behavioral questions | Conduct 2 Cloud Architecture mock interviews |

## Milestones & Checkpoints

- [ ] **End of Week 3:** Can successfully map out and configure a 3-tier VPC architecture from memory.
- [ ] **End of Week 5:** Understands the trade-offs between Object Storage, Block Storage, and File Storage.
- [ ] **End of Week 8:** Can articulate how to decouple an architecture using message queues and serverless functions.
- [ ] **End of Week 10:** Confidently lead a whiteboard session on migrating an on-premise monolith to the cloud.

## Company Recommendations

- **Cloud Providers (AWS/GCP/Azure):** Expect extremely deep technical questions on specific services, networking protocols, and limits.
- **Enterprise / Corporate:** Focus on migrations, compliance (HIPAA, SOC2), security perimeters, and cost-control.
- **Consultancies (Slalom, Deloitte):** Emphasis on broad knowledge, client communication, and understanding the "Well-Architected Framework."

## Interview Readiness Checklist

- [ ] Strong understanding of the Shared Responsibility Model.
- [ ] Can write complex IAM JSON policies.
- [ ] Prepared to discuss a time you optimized cloud costs.
- [ ] Deep knowledge of at least one cloud provider's core services.
