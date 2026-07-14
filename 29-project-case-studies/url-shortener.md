# URL Shortener Case Study

## Problem
Users need a way to take long, cumbersome URLs and convert them into short, shareable links. When a user clicks the short link, they should be seamlessly redirected to the original long URL. 

## Requirements
* **Functional:** 
  * Given a long URL, generate a shorter alias.
  * When users visit the short alias, redirect them to the original URL.
  * Custom aliases should be supported.
  * Links can expire.
* **Non-Functional:**
  * Highly available (if the service is down, all links break).
  * URL redirection should have minimal latency.
  * The system should handle a high volume of read requests (read-heavy, typically 100:1 read-to-write ratio).

## Architecture
1. **Client:** Sends a long URL to the API.
2. **API Gateway / Load Balancer:** Distributes traffic across multiple application servers.
3. **App Servers:** Handles the logic of encoding URLs (e.g., Base62 encoding) or checking for custom aliases.
4. **Database (Relational/NoSQL):** Stores the mapping of short URLs to long URLs, along with user metadata and expiration times.
5. **Cache (Redis/Memcached):** Stores frequently accessed short URLs to minimize database reads and reduce redirection latency.

## Trade-offs
* **Encoding (Base62 vs MD5):** Base62 encoding of an auto-incrementing ID is predictable but avoids collisions easily. Hashing (MD5) is unpredictable but can have collisions, requiring collision resolution logic.
* **Database Choice:** A relational DB (PostgreSQL) is easy for ACID compliance, but a NoSQL DB (DynamoDB/Cassandra) scales horizontally better for massive, unstructured read volumes. We chose NoSQL for ease of horizontal scaling, sacrificing complex query capabilities.

## Scaling Decisions
* **Caching Layer:** Added Redis to cache the top 20% most accessed URLs, handling 80% of the read traffic, significantly reducing database load.
* **Database Sharding:** Sharded the NoSQL database based on the hash of the short URL to distribute the massive read/write load evenly across multiple instances.

## Technology Choices
* **Backend:** Go or Node.js (high concurrency handling).
* **Database:** Cassandra or DynamoDB (highly available, scalable key-value storage).
* **Cache:** Redis.
* **ID Generation:** Key Generation Service (KGS) running independently to pre-generate unique IDs.

## Common Interview Questions
* How do you prevent URL collisions?
* How does the system handle rapid spikes in traffic for a single popular link?
* How do you design the Key Generation Service?

## Strong Answers
* "To prevent collisions, I designed a standalone Key Generation Service (KGS) that pre-generates unique IDs and stores them in a database. App servers load a chunk of unused IDs into memory, ensuring no two servers assign the same ID, completely eliminating collisions while keeping generation extremely fast."
* "For traffic spikes on a single link, the cache handles the bulk of the load. If the cache nodes are getting hot, we can introduce local in-memory caching on the application servers themselves for the absolute hottest keys."

## Weak Answers
* "I would just use a random string generator." *(Fails to address the high probability of collisions at scale.)*
* "I'll use MySQL and scale it up." *(Ignores the benefits of NoSQL for this specific key-value access pattern and the limits of vertical scaling.)*

## Hiring Manager Notes
Candidates should quickly recognize this is a read-heavy, highly available system. The differentiator is how they handle ID generation at scale. Top candidates will proactively suggest a KGS or discuss the intricacies of ZooKeeper for distributed ID generation.

## Possible Follow-up Questions
* How would you track analytics (clicks, geolocation) for each link?
* How do you safely delete expired URLs without impacting database performance?

## System Design Discussion
When presenting this, draw a clear distinction between the read path (redirection) and the write path (creation). Emphasize that the read path must be highly optimized. Discuss how a 301 (Permanent) vs. 302 (Temporary) HTTP redirect impacts both caching in the browser and analytics tracking on the server.
