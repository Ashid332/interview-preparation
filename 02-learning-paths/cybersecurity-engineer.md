# Cybersecurity Engineer Interview Learning Path

## Role Overview
Cybersecurity Engineers focus on protecting systems, networks, and data from threats. This role requires an adversarial mindset, knowledge of secure coding, networking protocols, and incident response. This 10-week path prepares you for AppSec, NetSec, and general Security Engineering roles.

## Prerequisites

| Skill Area | Expected Proficiency Level | Resources for Review |
|------------|----------------------------|----------------------|
| Networking | Intermediate (TCP/IP, OSI Model) | Network+ equivalent |
| Operating Systems | Intermediate (Linux/Windows Internals) | OS Fundamentals |
| Coding | Basic (Python, Bash, or Go) | Scripting basics |

## Path Overview

```mermaid
gantt
    title Security Engineer 10-Week Preparation Plan
    dateFormat  w
    axisFormat %W
    section Core Concepts
    Networking & Crypto   :a1, 0, 3w
    section AppSec
    Web Security & OWASP  :a2, after a1, 3w
    section Def & Offense
    Blue/Red Team Skills  :a3, after a2, 2w
    section Interview Prep
    Threat Modeling & Mocks:a4, after a3, 2w
```

## Weekly Roadmap

### Weeks 1-3: Core Networking & Cryptography
The fundamental building blocks of security.

| Week | Focus Area | Key Concepts | Practice Goal |
|------|------------|--------------|---------------|
| 1 | Network Security | Firewalls, IDS/IPS, VPNs, TLS/SSL handshake, Wireshark | Analyze a PCAP file to identify malicious traffic |
| 2 | OS Security | Linux permissions, Windows Active Directory, Privilege Escalation | Harden a basic Linux server |
| 3 | Cryptography | Symmetric/Asymmetric, Hashing, PKI, Salting | Implement a secure password hashing scheme (e.g., bcrypt) |

### Weeks 4-6: Application Security (AppSec)
Securing web applications and code.

| Week | Focus Area | Key Concepts | Practice Goal |
|------|------------|--------------|---------------|
| 4 | OWASP Top 10 | Injection, Broken Auth, XSS, CSRF, SSRF | Complete PortSwigger Web Security Academy modules |
| 5 | Secure Coding | Input validation, output encoding, secure defaults | Review a vulnerable code snippet and patch it |
| 6 | SAST / DAST | Static/Dynamic analysis, integrating security into CI/CD | Set up Semgrep in a GitHub Actions pipeline |

### Weeks 7-8: Defensive & Offensive Operations
Understanding how attackers operate to better defend against them.

| Week | Focus Area | Key Concepts | Action Item |
|------|------------|--------------|-------------|
| 7 | Offensive (Red Team) | Mitre ATT&CK framework, Penetration Testing basics | Complete 3 HackTheBox or TryHackMe machines |
| 8 | Defensive (Blue Team) | Incident Response lifecycle, SIEMs (Splunk/ELK), Log analysis | Draft an Incident Response plan for a ransomware attack |

### Weeks 9-10: Threat Modeling & Behavioral
Interview-specific preparation and whiteboarding.

| Week | Focus Area | Key Concepts | Action Item |
|------|------------|--------------|-------------|
| 9 | Threat Modeling | STRIDE, DREAD, mapping attack surfaces | Threat model an architecture (e.g., an Online Banking App) |
| 10 | Behavioral & Mocks | Ethical dilemmas, communication during a breach | Conduct 2 Security Design mock interviews |

## Milestones & Checkpoints

- [ ] **End of Week 3:** Can explain the TLS handshake step-by-step on a whiteboard.
- [ ] **End of Week 6:** Can identify and explain how to remediate XSS and SQLi vulnerabilities in source code.
- [ ] **End of Week 8:** Understand the phases of Incident Response (Preparation, Identification, Containment, Eradication, Recovery, Lessons Learned).
- [ ] **End of Week 10:** Confidently apply the STRIDE methodology to an arbitrary system architecture.

## Company Recommendations

- **Tech Companies (Meta, Google):** Heavy emphasis on AppSec, secure coding, and threat modeling scalable architectures.
- **Financial Institutions:** Focus on compliance, cryptography, identity & access management (IAM), and network perimeters.
- **Cybersecurity Vendors (Crowdstrike, Palo Alto):** Deep technical knowledge of OS internals, malware analysis, or low-level networking.

## Interview Readiness Checklist

- [ ] Strong understanding of the difference between Authentication and Authorization.
- [ ] Can clearly articulate how a buffer overflow works.
- [ ] Prepared to discuss your methodology for staying updated on the latest CVEs.
- [ ] Have 3+ STAR stories detailing times you successfully advocated for security best practices.
