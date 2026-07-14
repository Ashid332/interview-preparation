# CRM (Customer Relationship Management) Case Study

## Problem
Sales teams need a unified platform to manage leads, track interactions (emails, calls), visualize their sales pipeline, and automate follow-up tasks.

## Requirements
* **Functional:**
  * Contact and lead management.
  * Pipeline visualization (Kanban style).
  * Activity logging and email integration.
  * Role-based access control (RBAC).
* **Non-Functional:**
  * High data security and auditability.
  * Customizable fields and workflows.
  * Searchable records with low latency.

## Architecture
1. **Client:** SPA (Single Page Application) for complex UI interactions.
2. **API Gateway:** Handles rate limiting, authentication, and routing.
3. **Core Services:** Microservices for Contacts, Deals, Tasks, and Communications.
4. **Primary Database:** Relational database for structured, transactional data.
5. **Search Engine:** Elasticsearch cluster for fast, full-text search across all CRM entities.
6. **Audit Log Service:** Append-only data store tracking every change for compliance.

## Trade-offs
* **Monolith vs Microservices:** Started with a monolith for speed of iteration. As the team grew, we extracted the Email Integration and Notification services into microservices because they had completely different scaling profiles and failure modes compared to the core CRUD operations.
* **SQL vs NoSQL for Custom Fields:** Users need custom fields (e.g., "Favorite Color" for a lead). Used PostgreSQL's JSONB column type to store schemaless custom fields while maintaining relational integrity for core fields (ID, Name, Company), striking a balance between structure and flexibility.

## Scaling Decisions
* **Search Optimization:** Offloaded all complex search queries from PostgreSQL to Elasticsearch. We use a CDC (Change Data Capture) tool like Debezium to stream updates from Postgres to Elasticsearch asynchronously.
* **Tenant Isolation:** Adopted a "pool" multi-tenancy model where all customers share the same database, but introduced a "tenant_id" column on every table. As enterprise clients signed on, we migrated them to dedicated database instances (silo model) for better performance and security isolation.

## Technology Choices
* **Backend:** Java (Spring Boot) or C# (.NET) - excellent for enterprise RBAC and complex domain logic.
* **Database:** PostgreSQL.
* **Search:** Elasticsearch.
* **Event Streaming:** Kafka for CDC and async communication between services.

## Common Interview Questions
* How do you implement custom fields for different customers?
* How do you ensure users only see data they are authorized to see?
* How do you keep the search index in sync with the primary database?

## Strong Answers
* "For custom fields, I leverage the Entity-Attribute-Value (EAV) pattern or simply use JSON columns in a modern SQL database. JSON is generally faster to query and easier to index than EAV."
* "For RBAC, we implemented Row-Level Security (RLS) in PostgreSQL. The application passes the user's role and ID to the database context, and the DB automatically filters out unauthorized rows before they even reach the application layer."

## Weak Answers
* "I'll just query the SQL database using `LIKE '%search_term%'` for searching leads." *(Shows lack of understanding of performance issues with full table scans).*
* "I add a new column to the table every time a customer wants a custom field." *(Does not scale for a multi-tenant SaaS).*

## Hiring Manager Notes
CRMs are all about complex data models, permissions, and search. Look for candidates who understand how to structure data flexibly without sacrificing performance, and those who know when to introduce specialized tools like Elasticsearch.

## Possible Follow-up Questions
* How would you design a system to ingest thousands of leads from a CSV file asynchronously?
* How do you handle email threading when integrating with external providers like Gmail?

## System Design Discussion
Focus on the complexity of the data model. Be prepared to draw the schema relationships between Users, Organizations, Contacts, and Deals. Discuss the complexities of multi-tenancy and data isolation.
