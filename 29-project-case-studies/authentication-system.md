# Authentication System Case Study

## Problem
A company with multiple applications (web, mobile, internal tools) needs a centralized identity provider to handle user login, registration, password resets, and Single Sign-On (SSO), ensuring secure access across the entire ecosystem.

## Requirements
* **Functional:**
  * User registration and login (Email/Password, OAuth/Social Login).
  * Multi-Factor Authentication (MFA).
  * Issue and validate session tokens (JWT).
  * SSO across multiple company domains.
* **Non-Functional:**
  * Absolute highest security standards (protection against brute force, XSS, CSRF).
  * Extremely high availability (if Auth is down, no one can use any app).
  * Low latency (token validation happens on almost every API request).

## Architecture
1. **Client Apps:** Redirect users to the Auth Server for login.
2. **Auth Gateway:** Handles rate limiting and basic threat protection (WAF).
3. **Identity Provider (IdP) Service:** Core logic for verifying credentials, issuing tokens, and managing OAuth flows.
4. **User Database:** Securely stores user profiles and heavily hashed passwords (bcrypt/Argon2).
5. **Token Cache:** Redis cluster for storing token blocklists or active session data.
6. **Notification Service:** Sends emails/SMS for MFA and password resets.

## Trade-offs
* **Stateful Sessions vs Stateless JWTs:** 
  * *Stateful (Session IDs):* Secure, easy to revoke instantly, but requires a database/cache lookup on every request, creating a bottleneck.
  * *Stateless (JWT):* Highly scalable (services validate the token via cryptography without asking the DB), but hard to revoke before expiration.
  * *Decision:* Used a hybrid approach. Short-lived stateless JWTs (e.g., 15 mins) for API access, and long-lived stateful Refresh Tokens (stored securely as HTTP-only cookies) to get new JWTs. This balances security and scalability.

## Scaling Decisions
* **Decentralized Validation:** Because we use JWTs, the individual microservices validate the tokens themselves using a shared public key. This removes the IdP as a central bottleneck for read requests.
* **Geographical Distribution:** Auth requests are sensitive to latency. We deployed the IdP and read replicas of the user database across multiple geographic regions to ensure low-latency logins globally.

## Technology Choices
* **Framework:** Standardized identity solutions like Keycloak, Auth0, or AWS Cognito are preferred over building from scratch due to security risks. If building custom, Go or Java.
* **Cryptography:** RSA or ECDSA for signing JWTs. Argon2id for password hashing.
* **Database:** PostgreSQL for user data. Redis for the refresh token store and rate limiting counters.

## Common Interview Questions
* How do you securely store passwords?
* What happens if a JWT is stolen? How do you revoke it?
* Explain the OAuth 2.0 authorization code flow.

## Strong Answers
* "Passwords are never stored in plain text. We use a strong, slow hashing algorithm like Argon2id with a unique salt per user. This defends against rainbow table attacks and slows down brute-force cracking attempts on compromised databases."
* "If a JWT is stolen, it's valid until it expires. Because they are stateless, we can't 'revoke' them easily without defeating their purpose. Our defense is keeping their lifespan very short (15 mins). If we detect a compromised account, we instantly revoke the *Refresh Token* in the database. When the stolen JWT expires shortly after, the attacker cannot get a new one."

## Weak Answers
* "I'll encrypt the passwords." *(Passwords should be hashed, not encrypted. Reversible encryption is a massive security flaw).*
* "I store the JWT in local storage." *(Local storage is vulnerable to XSS attacks. Tokens should generally be stored in HttpOnly, Secure cookies).*

## Hiring Manager Notes
Security is paramount here. Candidates must not invent their own cryptography. They need to demonstrate a deep understanding of standard protocols (OAuth 2.0, OIDC, SAML), token lifecycles, and attack vectors (XSS, CSRF, MITM).

## Possible Follow-up Questions
* How would you design a system to detect anomaly logins (e.g., user logs in from New York, then 5 minutes later from Tokyo)?
* How do you handle database migrations for a system that can never have downtime?

## System Design Discussion
Be very precise about where tokens are stored on the client and how they are transported. Draw out the sequence diagram for an OAuth flow clearly. Discuss security best practices like rate limiting, WAFs, and secure cookie attributes.
