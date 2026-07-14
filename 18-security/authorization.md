# Authorization (AuthZ)

## Overview
Authorization (AuthZ) is the process of determining what an authenticated user or system is allowed to do. It answers the question, "Are you allowed to access this resource or perform this action?" Authorization happens *after* authentication. Common authorization models include Role-Based Access Control (RBAC), Attribute-Based Access Control (ABAC), and Access Control Lists (ACLs).

## Interview Questions

### Question 1: What is the difference between RBAC and ABAC?
* **Difficulty:** Medium
* **Frequency:** Medium
* **Companies:** Salesforce, AWS, Atlassian

**Excellent Answer:**
* **Role-Based Access Control (RBAC):** Permissions are tied to roles (e.g., Admin, Editor, Viewer), and users are assigned to roles. It's simple to manage for static hierarchical structures (e.g., all Editors can publish articles).
* **Attribute-Based Access Control (ABAC):** Permissions are granted based on a combination of attributes regarding the user, the resource, the environment, and the action. It is highly granular and dynamic. For example, "A user can edit a document IF the user's department matches the document's department AND the time is between 9 AM and 5 PM." ABAC is much more flexible but harder to implement and audit than RBAC.

**Common Mistakes:**
* Confusing AuthN (Authentication) with AuthZ (Authorization).
* Recommending ABAC for simple applications where RBAC is perfectly sufficient.

### Question 2: Explain the Principle of Least Privilege (PoLP).
* **Difficulty:** Easy
* **Frequency:** High
* **Companies:** Google, Microsoft, Banks

**Excellent Answer:**
The Principle of Least Privilege states that a user, process, or system should only be given the bare minimum access rights and permissions necessary to perform their legitimate function, and for the shortest duration necessary. For example, a web application connecting to a database should use an account that can only read/write specific tables, not a database administrator account with permission to drop tables. This minimizes the blast radius if an account is compromised.

**Common Mistakes:**
* Explaining it only in the context of human users, forgetting that it applies equally to microservices, IAM roles, and system processes.

## Real-World Applications
* **Cloud Infrastructure:** Configuring AWS IAM policies to allow a specific Lambda function to read from one specific S3 bucket and nothing else.
* **SaaS Permissions:** Implementing a document sharing system (like Google Docs) where users can be owners, editors, or viewers of individual documents.

## Practice Problems

| Problem | Type | Focus | Difficulty |
| :--- | :--- | :--- | :--- |
| Design a permission system for a Google Drive clone | System Design | ACLs, inheritance | Hard |
| Implement middleware to check user roles in an API | Coding | RBAC, API security | Easy |

## Hiring Manager Perspective
Managers want engineers who design authorization systems securely by default. A common failing in systems is Insecure Direct Object Reference (IDOR)—where a user can access another user's data just by changing an ID in a URL. Managers look for candidates who naturally include authorization checks at every layer, especially the data access layer.

## AI Interview Coach
**Prompt for ChatGPT/Claude/Gemini:**
> "Act as a Principal Engineer. Ask me how I would design an authorization system for a multi-tenant SaaS application that requires both coarse-grained roles and fine-grained resource-level permissions. Challenge me on scalability and caching of permissions."
