# Microsoft Azure

## Overview
Microsoft Azure is a premier cloud computing platform offering robust integration with the Microsoft ecosystem (Active Directory, .NET, Windows Server) alongside comprehensive support for open-source technologies, making it a favorite for enterprise IT environments.

## Interview Questions

### Question 1: What is Azure Active Directory (Azure AD/Entra ID), and how does it relate to Azure RBAC?
* **Difficulty:** Medium
* **Frequency:** High
* **Companies:** Microsoft, Walmart, Enterprise IT

**Excellent Answer:**
Azure AD (now Entra ID) is an identity and access management (IAM) service used to manage users, groups, and application service principals. Azure Role-Based Access Control (RBAC) is an authorization system built on Azure Resource Manager that provides fine-grained access management to Azure resources. Essentially, Azure AD authenticates *who* you are, and Azure RBAC determines *what* resources you can access and what actions you can perform on them.

**Common Mistakes:**
- Confusing traditional on-premise Windows Server Active Directory with the cloud-native Azure AD.
- Mixing up Azure AD roles (which manage identity/tenant resources) with Azure RBAC roles (which manage Azure resources like VMs and storage).

## Real-World Applications
Azure is heavily used for enterprise hybrid-cloud deployments, migrating legacy Windows applications, managing large-scale IoT networks, and enterprise data analytics via Synapse and Databricks.

## Practice Problems
| Problem | Description | Complexity | Link |
| --- | --- | --- | --- |

## Hiring Manager Perspective
Azure managers appreciate candidates who understand the nuances of the Microsoft ecosystem, particularly hybrid networking (VPN Gateway/ExpressRoute) and enterprise identity management. Governance (Azure Policies and Management Groups) is also a strong differentiator.

## AI Interview Coach
**ChatGPT/Claude/Gemini Prompt:**
> "Act as a Senior Cloud Architect interviewing me for an Azure role. Ask me detailed questions about implementing a hub-and-spoke network topology in Azure and how to secure it."
