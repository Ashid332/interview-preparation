# AWS Cheat Sheet

## Key Concepts
| Concept | Description |
|---|---|
| EC2 (Elastic Compute Cloud) | Virtual servers in the cloud (IaaS). |
| S3 (Simple Storage Service) | Highly scalable object storage. |
| Lambda | Serverless compute service (FaaS) that runs code in response to events. |
| VPC (Virtual Private Cloud) | Logically isolated section of the AWS Cloud. |
| IAM (Identity and Access Management) | Securely manage access to AWS services and resources. |

## Must-Know Items
- Compute choices: EC2 vs ECS/EKS vs Lambda.
- Database choices: RDS (SQL) vs DynamoDB (NoSQL) vs ElastiCache.
- Event-driven patterns: SQS, SNS, EventBridge.
- CDN and Edge: CloudFront, Route53.

## Common Interview Questions (Quick)
1. Design a scalable web architecture on AWS.
2. Difference between SQS and SNS?
3. How do you secure data at rest and in transit in S3?
4. Explain the difference between an Application Load Balancer and a Network Load Balancer.

## Critical Commands/Patterns
*Standard 3-Tier Architecture on AWS:*
- Web Tier: CloudFront + WAF -> ALB -> Auto-scaling group of EC2/Fargate in Public/Private subnets.
- App Tier: Internal ALB -> Auto-scaling group in Private subnets.
- Data Tier: Multi-AZ RDS + ElastiCache in Private subnets.

## Decision Framework
- **Storage:** S3 for objects (images, backups), EBS for block storage (attached to EC2), EFS for shared file storage across multiple EC2 instances.
- **Messaging:** SQS for queueing/buffering tasks (1:1), SNS for pub/sub fan-out (1:N).

## Common Mistakes
- Leaving S3 buckets public.
- Storing long-term static assets on EBS instead of S3.
- Not setting up billing alerts (surprise bills).
- Hardcoding IAM credentials in code instead of using Roles.

## One-Minute Review
- AWS provides building blocks. Know the core services for compute, storage, databases, and networking. Focus on IAM security, high availability (Multi-AZ), and decoupling via queues/topics.
