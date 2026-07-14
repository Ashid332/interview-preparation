# Authentication (AuthN)

## Overview
Authentication (AuthN) is the process of verifying the identity of a user, device, or system. It answers the question, "Are you who you say you are?" Common authentication methods include passwords, Multi-Factor Authentication (MFA), biometric scans, and single sign-on (SSO) protocols like OAuth 2.0, OpenID Connect (OIDC), and SAML.

## Interview Questions

### Question 1: How should passwords be stored securely in a database?
* **Difficulty:** Easy
* **Frequency:** Very High
* **Companies:** Every company

**Excellent Answer:**
Passwords should never be stored in plain text or using two-way encryption. They must be hashed using a strong, slow, cryptographic hashing algorithm designed specifically for passwords, such as bcrypt, Argon2, or scrypt. Additionally, every password must be "salted"—a unique random string appended to the password before hashing. Salting defends against pre-computed rainbow table attacks, and using slow algorithms defends against brute-force attacks by making computing the hash computationally expensive.

**Common Mistakes:**
* Suggesting MD5 or SHA-256 for passwords (these are fast algorithms, vulnerable to brute-forcing).
* Not mentioning salting.

### Question 2: Explain how JSON Web Tokens (JWT) work and their pros and cons.
* **Difficulty:** Medium
* **Frequency:** High
* **Companies:** Auth0, Meta, Netflix

**Excellent Answer:**
A JWT is a stateless, self-contained token used to securely transmit information as a JSON object. It consists of three parts: Header, Payload (claims like user ID and expiration), and Signature (created using a secret or public/private key pair to verify the token hasn't been tampered with).
* **Pros:** Stateless (no database lookup required to verify), easily scales across microservices, cross-domain friendly.
* **Cons:** Cannot be easily invalidated or revoked before expiration without building a stateful blocklist (which defeats the stateless purpose), payload is easily readable (Base64 encoded, not encrypted, so no sensitive data should be in it), token size can be large.

**Common Mistakes:**
* Believing JWTs are encrypted and can hide sensitive data (they are only signed).
* Failing to address the token revocation problem.

## Real-World Applications
* **Single Sign-On (SSO):** Implementing "Sign in with Google" using OAuth 2.0 and OpenID Connect.
* **Multi-Factor Authentication (MFA):** Requiring a Time-based One-Time Password (TOTP) from an authenticator app after verifying a password.

## Practice Problems

| Problem | Type | Focus | Difficulty |
| :--- | :--- | :--- | :--- |
| Implement secure password hashing | Coding | bcrypt, salting | Easy |
| Design a secure SSO flow using OAuth 2.0 | System Design | Auth flows, tokens | Hard |

## Hiring Manager Perspective
Managers look for candidates who understand that authentication is hard to get right and often prefer leveraging established identity providers (like Auth0, AWS Cognito, or Okta) over rolling their own crypto and auth systems. They value deep knowledge of session management and token lifecycles.

## AI Interview Coach
**Prompt for ChatGPT/Claude/Gemini:**
> "I want to practice explaining authentication protocols. Ask me to compare and contrast session-based authentication (cookies) with token-based authentication (JWTs). Evaluate my explanation of the security trade-offs for each approach."
