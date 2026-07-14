# AI Engineering Cheat Sheet

## Key Concepts
| Concept | Description |
|---|---|
| LLM (Large Language Model) | Foundation models trained on vast text data to predict the next token (e.g., GPT-4, Llama 3). |
| RAG (Retrieval-Augmented Generation) | Combining LLM generation with external knowledge retrieval to reduce hallucinations. |
| Prompt Engineering | Designing inputs to elicit optimal responses from an LLM. |
| Fine-tuning | Adapting a pre-trained model on a smaller, domain-specific dataset. |
| Vector Database | Databases optimized for storing and querying high-dimensional vectors (embeddings) via similarity search. |

## Must-Know Items
- The RAG pipeline: Document loading -> Chunking -> Embedding -> Vector Store -> Retrieval -> Prompt formulation -> LLM Generation.
- Embeddings: Representing text as dense vectors where semantic similarity = geometric proximity.
- Hallucinations and mitigation strategies.
- Agentic Workflows (ReAct pattern, Tool use).

## Common Interview Questions (Quick)
1. Explain how RAG works and its benefits over fine-tuning.
2. How do you evaluate the quality of an LLM's output?
3. What is chunking, and why is it important in RAG?
4. Describe the ReAct (Reasoning and Acting) prompting pattern.

## Critical Commands/Patterns
*Basic RAG Pattern (Pseudo-code):*
```python
query = "What is the company's leave policy?"
query_embedding = embed_model.get_embedding(query)
# Retrieve top-k similar chunks
docs = vector_db.similarity_search(query_embedding, k=3)
context = "\n".join([doc.text for doc in docs])

prompt = f"Answer the query based ONLY on the context.\nContext: {context}\nQuery: {query}"
response = llm.generate(prompt)
```

## Decision Framework
- **Prompting vs RAG vs Fine-tuning:** 
  - Need specific formatting or tone? Prompting / Few-shot.
  - Need to inject private, dynamic knowledge? RAG.
  - Need the model to learn a new task, domain jargon, or optimize latency/cost heavily? Fine-tuning.

## Common Mistakes
- Using fine-tuning to inject new facts (models struggle to memorize facts via fine-tuning; use RAG instead).
- Poor chunking strategies (e.g., splitting mid-sentence), leading to loss of context in RAG.
- Not evaluating RAG systems systematically (e.g., using frameworks like RAGAS).

## One-Minute Review
- AI Engineering bridges software engineering and AI. Focus heavily on orchestrating LLMs via API, building robust RAG pipelines, managing vector stores, and ensuring safe, predictable outputs.
