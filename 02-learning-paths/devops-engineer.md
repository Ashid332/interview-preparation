# DevOps Engineer Interview Learning Path

## Role Overview
DevOps Engineers sit at the intersection of software development and IT operations. They focus on automating infrastructure, optimizing CI/CD pipelines, and ensuring system reliability and observability. This 10-week path prepares you for platform engineering, DevOps, and SRE roles.

## Prerequisites

| Skill Area | Expected Proficiency Level | Resources for Review |
|------------|----------------------------|----------------------|
| Linux/Unix | Advanced | Linux Command Line tutorials |
| Scripting | Intermediate (Bash/Python) | Bash scripting guides |
| Version Control | Advanced (Git) | Git documentation |

## Path Overview

```mermaid
gantt
    title DevOps Engineer 10-Week Preparation Plan
    dateFormat  w
    axisFormat %W
    section Core OS & Scripting
    Linux & Bash          :a1, 0, 2w
    section Infrastructure
    Containers & IaC      :a2, after a1, 3w
    section CI/CD & Deploy
    Pipelines & Automation:a3, after a2, 2w
    section SRE Fundamentals
    Monitoring & Mocks    :a4, after a3, 3w
```

## Weekly Roadmap

### Weeks 1-2: Core OS, Networking & Scripting
Solidifying the foundational layers of infrastructure.

| Week | Focus Area | Key Concepts | Practice Goal |
|------|------------|--------------|---------------|
| 1 | Linux Internals | File systems, permissions, processes (top, ps), systemd | Write a Bash script to automate log rotation |
| 2 | Networking & Security | DNS, TCP/IP, SSH, iptables, Subnetting | Set up a secure SSH server with key-based auth only |

### Weeks 3-5: Containerization & Infrastructure as Code
Moving from manual configurations to automated, reproducible environments.

| Week | Focus Area | Key Concepts | Practice Goal |
|------|------------|--------------|---------------|
| 3 | Docker & Containers | Dockerfiles, multi-stage builds, Docker Compose | Containerize a multi-tier application (Web + DB) |
| 4 | Kubernetes (K8s) Basics| Pods, Deployments, Services, Ingress, ConfigMaps | Deploy the containerized app to a local Minikube cluster |
| 5 | Infrastructure as Code | Terraform, Ansible, State Management, Modules | Provision an AWS/GCP VPC and EC2 instance via Terraform |

### Weeks 6-7: CI/CD & Automation
Streamlining the path to production.

| Week | Focus Area | Key Concepts | Action Item |
|------|------------|--------------|-------------|
| 6 | CI/CD Pipelines | GitHub Actions, GitLab CI, Jenkins, build caching | Write a GitHub Action to build and test a Docker image |
| 7 | Deployment Strategies | Blue/Green, Canary deployments, Rollbacks | Implement a Blue/Green deployment script for Kubernetes |

### Weeks 8-10: SRE Fundamentals, Monitoring, & Mocks
Ensuring uptime, responding to incidents, and interview polish.

| Week | Focus Area | Key Concepts | Action Item |
|------|------------|--------------|-------------|
| 8 | Observability & SRE | Prometheus, Grafana, ELK Stack, SLIs/SLOs/SLAs | Set up Prometheus to scrape metrics from a web app |
| 9 | Incident Response | Post-mortems, blameless culture, disaster recovery | Draft 5 STAR stories focusing on incident resolution |
| 10 | System Design & Mocks | Architecting for high availability | Conduct 2 Infrastructure Design Mock Interviews |

## Milestones & Checkpoints

- [ ] **End of Week 2:** Can troubleshoot networking issues using `curl`, `ping`, `traceroute`, and `netstat`/`ss`.
- [ ] **End of Week 5:** Can write a clean, modular Terraform configuration to spin up basic cloud infrastructure.
- [ ] **End of Week 7:** Can explain the complete CI/CD lifecycle from git push to production deployment.
- [ ] **End of Week 10:** Confidently define the differences between SLAs, SLOs, and SLIs.

## Company Recommendations

- **Cloud-Native Startups:** Heavy emphasis on Kubernetes, GitHub Actions, and GitOps (ArgoCD).
- **Enterprise / Legacy:** Expect questions on Jenkins, Ansible, Linux troubleshooting, and hybrid-cloud architectures.
- **Fintech / Healthcare:** Focus on compliance, secure pipelines (DevSecOps), and strict access controls.

## Interview Readiness Checklist

- [ ] Can write a multi-stage Dockerfile from scratch.
- [ ] Understand the Linux boot process and process management.
- [ ] Can articulate a blameless post-mortem process.
- [ ] Comfortable whiteboarding a high-availability infrastructure architecture.
