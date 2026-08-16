# Kubernetes

## Overview
Kubernetes (K8s) is an open-source container orchestration engine for automating deployment, scaling, and management of containerized applications. It groups containers that make up an application into logical units for easy management and discovery.

## Interview Questions

### Question 1: Describe the architecture of a Kubernetes cluster and its core components.
* **Difficulty:** Medium
* **Frequency:** High
* **Companies:** Google, Uber, Spotify

**Excellent Answer:**
A K8s cluster consists of a Control Plane and Worker Nodes. The Control Plane manages the cluster and includes the API Server (frontend for all commands), etcd (distributed key-value store for state), Scheduler (assigns pods to nodes), and Controller Manager (maintains desired state). Worker nodes run the applications and include the Kubelet (communicates with control plane), Kube-proxy (handles networking), and a container runtime (like containerd).

**Common Mistakes:**
- Forgetting to mention etcd and its critical role in state management.
- Confusing the roles of the Kubelet and Kube-proxy.

## Real-World Applications
Kubernetes is the standard for managing large-scale microservice deployments. It handles self-healing, automated rollouts and rollbacks, horizontal scaling based on metrics, and secrets/configuration management.

## Practice Problems
| Problem | Description | Complexity | Link |
| --- | --- | --- | --- |

## Hiring Manager Perspective
Managers evaluate your practical troubleshooting experience. They want engineers who not only know how to deploy objects via `kubectl apply` but also deeply understand RBAC, network policies, and how to debug failing pods effectively.

## AI Interview Coach
**ChatGPT/Claude/Gemini Prompt:**
> "Act as a Cloud Infrastructure Manager. Give me a scenario where a production Kubernetes cluster is experiencing node exhaustion. Ask me step-by-step how I would diagnose, mitigate, and resolve the issue."
