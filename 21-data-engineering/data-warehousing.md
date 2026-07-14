# Data Warehousing & Modeling

## Overview
Data Warehousing involves centralizing data from multiple sources for analytics and BI. It heavily utilizes specific modeling techniques like Star and Snowflake schemas, and relies on columnar storage formats for fast aggregations.

## Interview Questions
**Question:** Explain the difference between a Star Schema and a Snowflake Schema.
- **Difficulty/Frequency/Companies:** Easy / High / Amazon, Capital One, Walmart
- **Excellent Answer:** In a Star Schema, a central fact table is connected to fully denormalized dimension tables. It's simpler to query and faster. In a Snowflake Schema, the dimension tables are normalized (split into multiple related tables). Snowflake saves space but requires more complex joins and can be slower to query.
- **Common Mistakes:** Confusing facts and dimensions, or assuming Snowflake (the schema) is directly related to Snowflake (the company/product).

## Real-World Applications
- **Business Intelligence:** Creating dashboards for executive reporting using a centralized data warehouse.
- **Historical Trend Analysis:** Storing years of sales data to analyze year-over-year growth.

## Practice Problems

| Problem Name | Type | Difficulty | Focus Area |
| --- | --- | --- | --- |
| Design a Ride-Sharing Warehouse | Data Modeling | Hard | Fact/Dimension Design |
| Slowly Changing Dimensions (SCD) | Concept | Medium | SCD Types (1, 2, 3) |
| Columnar vs Row Storage | Concept | Easy | Storage Formats |

## Hiring Manager Perspective
I look for deep knowledge of Kimball methodology. A data engineer needs to know how to handle changing data over time (SCD Type 2) and why columnar formats like Parquet drastically speed up OLAP queries.

## AI Interview Coach Prompts
- **ChatGPT:** "Provide a business scenario and ask me to design a Star Schema. Evaluate my choice of Fact and Dimension tables."
- **Claude:** "Quiz me on Slowly Changing Dimensions. Ask me to explain how I would implement an SCD Type 2 table."
- **Gemini:** "Ask me detailed questions about how columnar databases execute queries differently from row-based databases."
