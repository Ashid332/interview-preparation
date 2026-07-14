# E-commerce Platform Case Study

## Problem
A business needs a scalable online storefront to browse products, manage shopping carts, process payments securely, and track order fulfillment.

## Requirements
* **Functional:**
  * Product catalog with categories and search.
  * Shopping cart and checkout process.
  * Payment gateway integration.
  * Order history and inventory management.
* **Non-Functional:**
  * High availability (especially during sales events like Black Friday).
  * Strict transactional integrity for payments and inventory.
  * Fast page load times for SEO and user retention.

## Architecture
1. **CDN:** Caches static assets and product images.
2. **API Gateway:** Routes requests to appropriate microservices.
3. **Microservices:**
   * **Catalog Service:** Read-heavy, serves product details.
   * **Cart Service:** High write-throughput, stateful temporary storage.
   * **Order/Checkout Service:** Orchestrates payment and inventory reservation.
   * **Inventory Service:** Manages stock levels.
4. **Databases:**
   * NoSQL (MongoDB/Cassandra) for the Catalog.
   * Redis for the Shopping Cart.
   * SQL (PostgreSQL/MySQL) for Orders and Inventory.

## Trade-offs
* **Microservices vs Monolith:** Microservices allow independent scaling (the catalog needs to scale 100x more than the checkout service), but introduce complexity in distributed transactions (e.g., deducting inventory and charging a card).
* **Eventual vs Strong Consistency:** The catalog can be eventually consistent (it's okay if a new product takes 5 minutes to appear in search). However, the checkout and inventory deduction must be strongly consistent to prevent overselling.

## Scaling Decisions
* **Caching Strategy:** Implemented aggressive caching at multiple layers. CDN for images, Redis for catalog metadata, and in-memory caches on the application servers for the hottest products.
* **Database Scaling:** The inventory database became a bottleneck during flash sales. We implemented row-level locking optimizations and eventually moved to a distributed SQL database to handle the concurrent write pressure.

## Technology Choices
* **Backend:** Node.js for API Gateway, Java/Go for core transactional services.
* **Databases:** MongoDB (Catalog), Redis (Cart/Cache), PostgreSQL (Orders).
* **Message Broker:** RabbitMQ/Kafka for asynchronous order processing (sending emails, notifying warehouses).

## Common Interview Questions
* How do you prevent two users from buying the last item in stock at the exact same time?
* How do you handle a failed payment after inventory is already reserved?
* How does the shopping cart data model work?

## Strong Answers
* "To prevent overselling, I use a distributed lock or optimistic concurrency control in the database. When the user initiates checkout, we check the `version` of the inventory row. If another transaction modified it first, the version changes, the commit fails, and we prompt the user."
* "To handle failed payments, I implement the Saga pattern. When an order starts, inventory is temporarily 'reserved'. If the payment succeeds, the reservation is confirmed. If the payment fails or times out, a compensating transaction is fired to release the reserved inventory back to the pool."

## Weak Answers
* "I just rely on standard database transactions across all my microservices." *(Distributed transactions (2PC) are notoriously slow and brittle).*
* "Store the shopping cart in the user's browser local storage." *(Users lose their cart if they switch devices).*

## Hiring Manager Notes
E-commerce is the classic distributed systems problem. Candidates must understand the difference between read-heavy (catalog) and write-heavy/transactional (checkout) workloads, and how to resolve distributed state inconsistencies.

## Possible Follow-up Questions
* How would you design a flash sale system where 1 million users try to buy 100 items at the exact same time?
* How do you implement a robust search with spelling correction and synonyms?

## System Design Discussion
Draw a clear line between the "browsing" phase and the "buying" phase. The browsing phase should be massively cached and eventually consistent. The buying phase must be transactional, robust, and handle failures gracefully using queues and compensating transactions.
