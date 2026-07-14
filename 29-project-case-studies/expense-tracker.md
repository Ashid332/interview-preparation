# Expense Tracker Case Study

## Problem
Users need a tool to manually log daily expenses, categorize them, set monthly budgets, and view historical spending trends via reports and charts.

## Requirements
* **Functional:**
  * Add, edit, delete expenses.
  * Create custom categories and budgets.
  * Generate monthly/yearly summaries.
  * Support multiple currencies and daily exchange rates.
* **Non-Functional:**
  * High data integrity and consistency (it's financial data).
  * Fast read performance for generating reports.
  * Offline support for mobile clients.

## Architecture
1. **Client (Mobile/Web):** Features a local SQLite database for offline capabilities.
2. **API Gateway:** Routes REST/GraphQL requests, handles authentication.
3. **Application Servers:** Process CRUD operations and business logic (budget alerts).
4. **Relational Database:** PostgreSQL or MySQL for strict ACID compliance.
5. **Sync Service:** A dedicated worker that resolves conflicts when clients come back online and sync their local databases with the server.

## Trade-offs
* **Relational vs NoSQL:** Chose a relational database because financial transactions require strong consistency, ACID properties, and complex JOINs for reporting, which outweighs the horizontal scaling benefits of NoSQL in this context.
* **Real-time sync vs Background sync:** Implemented background synchronization to allow the app to feel lightning-fast locally, at the cost of potential merge conflicts if the user edits the same expense on two different devices while offline.

## Scaling Decisions
* **Read Replicas:** As the user base grows, reporting queries become heavy. We offload all analytical and reporting queries (e.g., generating end-of-year summaries) to read replicas, keeping the primary database free for high-throughput writes.
* **Caching:** Cached static data (like category lists and historical exchange rates) using Redis to reduce database hits.

## Technology Choices
* **Database:** PostgreSQL for robust data integrity and advanced JSON support if needed.
* **Backend:** Python (Django) or Java (Spring Boot) for rapid development and stable ORM tools.
* **API:** GraphQL, allowing clients to query exactly the fields they need for different dashboard views, reducing over-fetching.

## Common Interview Questions
* How do you handle offline mode and synchronization?
* What happens if a user submits an expense, the network drops, and they submit it again?
* How do you design the database schema for handling multiple currencies?

## Strong Answers
* "To handle offline sync and prevent duplicates, I would generate a unique UUID on the client side when the expense is created. Even if the network drops and the client retries, the server will see the same UUID and treat it as an idempotent request, safely ignoring the duplicate."
* "For multi-currency, every transaction is saved with its original currency code, the amount, and the exchange rate relative to the user's base currency *at the time of the transaction*. This ensures historical reports don't fluctuate based on today's exchange rates."

## Weak Answers
* "I'll just use MongoDB because it's easier to set up." *(Misses the need for relational integrity in financial apps).*
* "If there's a conflict during sync, I'll just overwrite the server data." *(Fails to consider complex merge scenarios and user experience).*

## Hiring Manager Notes
This is a standard CRUD application, but the complexity comes from offline-first architecture, concurrency, and idempotency. Candidates should demonstrate a solid grasp of database design and how to handle network instability.

## Possible Follow-up Questions
* How would you add a feature to automatically parse receipts from images?
* How would you handle sharing an expense ledger between two users (e.g., a couple)?

## System Design Discussion
During the presentation, highlight your focus on data accuracy and user experience. Emphasize how an offline-first approach requires careful handling of API design (idempotency keys) and database schema design (client-generated IDs).
