# DevOps Cheat Sheet

## Key Concepts
| Concept | Description |
|---|---|
| CI/CD | Continuous Integration (merging and testing code automatically) and Continuous Deployment/Delivery (automating releases). |
| Infrastructure as Code (IaC) | Managing and provisioning infrastructure through machine-readable definition files (Terraform, CloudFormation). |
| Observability | Measuring internal states of a system based on external outputs (Logs, Metrics, Traces). |
| Kubernetes (K8s) | Container orchestration system for automating software deployment, scaling, and management. |

## Must-Know Items
- CI/CD pipeline stages (Lint, Test, Build, Push, Deploy).
- Terraform state files and why they are important.
- The 3 Pillars of Observability: Logs (events), Metrics (aggregations), Traces (request path).
- Blue-Green and Canary deployment strategies.

## Common Interview Questions (Quick)
1. Explain what happens when a developer pushes code to the main branch (CI/CD flow).
2. What is Infrastructure as Code and what are its benefits?
3. How do you implement a zero-downtime deployment?
4. What are the key components of a Kubernetes cluster?

## Critical Commands/Patterns
*Kubernetes Basic Concepts:*
- Pod: Smallest deployable unit (usually one container).
- Deployment: Manages replicas of Pods and handles rollouts.
- Service: Network abstraction to expose Pods.

```bash
# Basic K8s commands
kubectl get pods
kubectl apply -f deployment.yaml
kubectl logs <pod-name>
```

## Decision Framework
- **Deployment Strategy:** 
  - Rolling Update: Standard K8s default, slow but safe. 
  - Blue-Green: Zero downtime, fast switch, requires 2x resources. 
  - Canary: Route 5% traffic to new version, monitor, then scale up. Best for risk mitigation.

## Common Mistakes
- Storing secrets in plain text in git repositories or IaC files.
- Lack of resource limits in containers, allowing one bad container to crash a node.
- Over-alerting, leading to alert fatigue for on-call engineers.

## One-Minute Review
- DevOps is a culture of automation and collaboration. Focus on CI/CD pipelines, IaC (Terraform), container orchestration (K8s), and solid observability practices to ensure system reliability.
