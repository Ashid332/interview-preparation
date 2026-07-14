# Web Security

## Overview
Web security focuses on protecting web applications and APIs from vulnerabilities and attacks. Interviewers frequently evaluate a candidate's knowledge of the OWASP (Open Web Application Security Project) Top 10, which outlines the most critical security risks to web applications, including Injection, Cross-Site Scripting (XSS), and Cross-Site Request Forgery (CSRF).

## Interview Questions

### Question 1: What is Cross-Site Scripting (XSS) and how do you prevent it?
* **Difficulty:** Medium
* **Frequency:** Very High
* **Companies:** Meta, Google, Twitter

**Excellent Answer:**
XSS occurs when an application includes untrusted, user-supplied data in a web page without proper validation or escaping. This allows an attacker to execute malicious JavaScript in the victim's browser, potentially stealing session cookies or performing actions on behalf of the user. 
To prevent it:
1. **Context-Aware Output Encoding:** Escape all user input before rendering it in the HTML, CSS, or JavaScript context. Modern frameworks (like React or Angular) do this automatically by default.
2. **Content Security Policy (CSP):** Use an HTTP response header that restricts which scripts can be executed and from where they can be loaded.
3. **HttpOnly Cookies:** Set the `HttpOnly` flag on session cookies so they cannot be accessed via JavaScript (`document.cookie`), mitigating the impact of a successful XSS attack.

**Common Mistakes:**
* Relying solely on input validation/sanitization instead of output encoding.
* Not knowing that modern frontend frameworks handle most basic XSS prevention natively.

### Question 2: What is Cross-Site Request Forgery (CSRF) and how is it mitigated?
* **Difficulty:** Medium
* **Frequency:** High
* **Companies:** Stripe, PayPal, Auth0

**Excellent Answer:**
CSRF is an attack that tricks a victim's browser into executing an unwanted action on a trusted site where the user is currently authenticated. Because browsers automatically send session cookies with requests, if an attacker tricks a user into clicking a link, the bank site receives a legitimate-looking request.
Mitigations include:
1. **Anti-CSRF Tokens:** The server generates a unique, unpredictable token included in hidden form fields or headers. The server validates this token on state-changing requests (POST/PUT/DELETE).
2. **SameSite Cookie Attribute:** Setting `SameSite=Lax` or `SameSite=Strict` on session cookies prevents the browser from sending cookies along with cross-site requests. This is the modern, highly effective defense.

**Common Mistakes:**
* Confusing XSS (stealing data/executing scripts) with CSRF (forcing unauthorized actions).
* Thinking CORS (Cross-Origin Resource Sharing) prevents CSRF (CORS protects reading data, not sending requests).

## Real-World Applications
* **Secure API Design:** Using parameterized queries (prepared statements) using ORMs to completely eliminate SQL Injection vulnerabilities.
* **Frontend Security:** Implementing strict CSP headers in a Next.js application to block inline scripts and unauthorized external resources.

## Practice Problems

| Problem | Type | Focus | Difficulty |
| :--- | :--- | :--- | :--- |
| Identify vulnerabilities in a provided snippet | Code Review | XSS, SQLi | Medium |
| Explain how to bypass a weak CSRF defense | Security | Attack vectors | Hard |

## Hiring Manager Perspective
Managers expect full-stack and backend engineers to have a solid grasp of web vulnerabilities. A candidate who doesn't know what SQL Injection or XSS is, or how to prevent them, is often an automatic rejection, as they represent a significant risk to the company's data.

## AI Interview Coach
**Prompt for ChatGPT/Claude/Gemini:**
> "Test my knowledge of the OWASP Top 10. Give me three different code snippets (one frontend, two backend) that contain common web vulnerabilities. Ask me to identify the vulnerability, explain the exploit, and provide the secure, corrected code."
