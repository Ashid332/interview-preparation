# System Design Mock Interview

## Format/Duration/Difficulty
* **Format:** System Design
* **Duration:** 60 minutes
* **Difficulty:** Hard

## Round Setup
* **Role:** Senior Software Engineer
* **Topic:** Scalable Architecture
* **Question:** Design a URL Shortener service (like bit.ly).

## The Interview

**Interviewer:** Let's design a URL shortening service. Users should be able to input a long URL and get a short one back, and when they visit the short URL, they redirect to the long one.

**Candidate:** Okay. Let's start with requirements. 
Functional:
1. Given a URL, return a shorter alias.
2. When accessing the alias, redirect to the original URL.
3. Custom short links optional? (Interviewer: Yes, let's include it).
4. Links expire? (Interviewer: No, they exist forever for now).

Non-Functional:
1. Highly available. Redirects need to be fast.
2. Scalable. We might have billions of links.
3. Read-heavy. The ratio of read to write is probably 100:1.

**Interviewer:** Good. What about traffic estimates?

**Candidate:** Let's assume 100 million new URLs created per month. 
With 100:1 ratio, that's 10 billion redirects per month.
QPS for writes: 100M / (30 * 24 * 3600) ≈ 40 URLs/sec.
QPS for reads: 10B / (30 * 24 * 3600) ≈ 4,000 URLs/sec.
Storage: 100M URLs * 5 years * 500 bytes per record ≈ 300 TB.

**Interviewer:** The estimates look reasonable. How would you design the core API and data model?

**Candidate:** 
API:
- `createShortUrl(longUrl, customAlias=null, userId)` -> returns `shortUrl`
- `getUrl(shortUrl)` -> returns `longUrl` (via 301/302 HTTP redirect)

Database: We need a NoSQL database or a relational one. Since it's billions of rows and minimal relationships, a NoSQL store like DynamoDB or Cassandra would be great for scalability, but a sharded PostgreSQL could also work. Let's go with a NoSQL store.
Schema:
- `hash` (Partition Key) - String (the short url)
- `original_url` - String
- `creation_date` - Timestamp
- `user_id` - Integer

**Interviewer:** How do you generate the short URL hash?

**Candidate:** We can use base62 encoding (A-Z, a-z, 0-9). 7 characters in base62 gives us 62^7 ≈ 3.5 trillion combinations, which is plenty.
To generate it, we have two approaches:
1. Hash the long URL (MD5/SHA256) and take the first 7 base62 chars. Problem: Collisions.
2. Key Generation Service (KGS). A standalone service that pre-generates random 7-character strings and stores them in a database. When a new request comes, we just take an unused key. This eliminates collisions and is very fast.

**Interviewer:** KGS is a good approach. Let's draw out the architecture. How do you handle the read-heavy load?

**Candidate:** Since it's read-heavy, caching is critical. I'd put a Redis cluster in front of the database. 
1. Client hits Load Balancer.
2. Request goes to Read API Server.
3. Server checks Redis. If cache hit, return 301 redirect.
4. If cache miss, fetch from DB, update Redis, return redirect.
We can use an LRU eviction policy for the cache, holding the top 20% of most accessed URLs.

**Interviewer:** Why 301 vs 302 redirect?

**Candidate:** 301 is a permanent redirect, so browsers will cache it. It reduces load on our servers, but we lose analytics on how often a link is clicked. 302 is temporary, so all requests hit our server, which is better if analytics is a priority. Given our scale, 301 might be safer for infrastructure, but product usually wants analytics, so 302 is often chosen.

## Interviewer Feedback
* **Score:** 4.5/5 (Strong Hire)
* **Strengths:** 
    * Excellent capacity estimation and requirement gathering.
    * Identified the KGS pattern to solve collisions efficiently.
    * Understood the trade-offs between 301 and 302 redirects.
    * Correctly identified the read-heavy nature and applied caching appropriately.
* **Areas for Improvement:** 
    * Could have discussed database sharding strategies in more detail for the NoSQL store.

## Improved Answer
For database scaling, candidate could mention: "If using a relational DB, we would shard based on the first character of the hash, or use consistent hashing to distribute the load across multiple database instances."

## Hiring Manager Notes
Shows strong architectural intuition. Communicates trade-offs well. Excellent candidate for Senior Engineer.
