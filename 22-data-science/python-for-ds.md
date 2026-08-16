# Python for Data Science

## Overview
Data Scientists need to be proficient in Python, specifically the data stack: Pandas, NumPy, and Scikit-Learn. Interviews test your ability to manipulate dataframes efficiently, handle missing data, write vectorized operations, and structure clean code.

## Interview Questions

### Q1: How does memory management work in Pandas, and how do you optimize it for large datasets?
**Difficulty:** Hard | **Frequency:** Medium | **Companies:** Netflix, Two Sigma, Databricks

**Excellent Answer:**
Pandas loads the entire dataset into RAM. If the data is larger than RAM, you will get an OutOfMemory error. To optimize:
1. **Downcasting:** Convert `float64` to `float32` and `int64` to `int32` or `int8` if the range of values allows.
2. **Categoricals:** Convert string columns with low cardinality (few unique values) to the `category` data type. This stores the strings once and uses integer pointers, saving massive amounts of memory.
3. **Chunking:** Read large files in chunks (`pd.read_csv(..., chunksize=N)`) and process them iteratively.
4. **Alternatives:** If it's truly big data, I would switch to Polars, Dask, or PySpark which handle out-of-core computation.

**Common Mistakes:**
- Suggesting iterating through rows with `iterrows()` (anti-pattern, very slow).
- Not understanding the difference between object types and string types.

## Real-World Applications
- Processing daily logs of terabyte-scale user activity on a local machine before moving to the cloud.
- Merging and grouping multiple large time-series datasets.

## Practice Problems

| Problem | Description | Difficulty | Link |
|---|---|---|---|
| Vectorization | Rewrite a `for` loop using NumPy vectorized operations | Medium | None |
| GroupBy Aggregation | Complex multi-level grouping and aggregation in Pandas | Medium | None |

## Hiring Manager Perspective
Anyone can write a Pandas script that works on 1MB of data. I want to see if the candidate knows how to write efficient, vectorized code that won't crash our production servers when applied to 10GB of data.

## AI Interview Coach
**ChatGPT/Claude/Gemini Prompts:**
- "Generate 5 advanced Pandas coding exercises focusing on complex joins and window functions."
- "What are the most common anti-patterns in Python data science code?"
