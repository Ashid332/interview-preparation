# AI Engineer Mock Interview

## Format/Duration/Difficulty
* **Format:** ML Architecture & NLP
* **Duration:** 60 minutes
* **Difficulty:** Hard

## Round Setup
* **Role:** Machine Learning / AI Engineer
* **Topic:** LLM Application Design
* **Question:** Design a RAG (Retrieval-Augmented Generation) system for internal company documents.

## The Interview

**Interviewer:** We want to build an internal chatbot that can answer questions based on our company's HR and engineering docs. How would you design this system?

**Candidate:** This is a classic RAG use case. We need two main pipelines: an ingestion pipeline to process the documents, and an inference pipeline to answer user queries.

**Interviewer:** Walk me through the ingestion pipeline first.

**Candidate:** 
1. **Data Loading:** We pull PDFs, Confluence pages, and Markdown files.
2. **Chunking:** We split these documents into smaller chunks. Since LLMs have context limits, we might chunk by paragraphs or use a semantic chunker (like LangChain's recursive character splitter) with maybe 1000 tokens and a 200-token overlap to preserve context between chunks.
3. **Embedding:** We pass these chunks through an embedding model (like OpenAI's `text-embedding-3-small` or an open-source model like `all-MiniLM-L6-v2`) to get vector representations.
4. **Vector Database:** We store the chunks and their vectors in a vector database like Pinecone, Milvus, or pgvector. We also store metadata (source URL, document type, access permissions).

**Interviewer:** Why store access permissions in metadata?

**Candidate:** For security. If an intern asks a question, the retrieval system shouldn't pull chunks from confidential executive documents. We use metadata filtering at query time before performing the vector similarity search.

**Interviewer:** Great point. Now explain the inference pipeline.

**Candidate:** 
1. User asks a question.
2. We embed the user's question using the *exact same* embedding model used in ingestion.
3. We query the Vector DB for the top K most similar chunks (using cosine similarity), applying user-based metadata filters.
4. We take these retrieved chunks and inject them into a prompt template: "Answer the user's question using ONLY the following context... [Context] ... Question: [Question]".
5. We send this prompt to an LLM (like GPT-4 or Claude) and return the response to the user.

**Interviewer:** What if the user asks a follow-up question like "Can you explain the second point more?"

**Candidate:** Ah, standard RAG is stateless. We need conversational memory. Before step 2, we take the user's raw question and their chat history, and pass it to a smaller LLM to "rephrase" it into a standalone query. So "Can you explain the second point more?" becomes "Can you explain the vacation rollover policy mentioned previously?" Then we embed *that* standalone query.

**Interviewer:** How would you evaluate the quality of this system?

**Candidate:** Evaluating generative AI is tough. I'd use a framework like RAGAS. We can measure:
1. **Context Precision:** Did we retrieve the relevant documents?
2. **Context Recall:** Did we retrieve *all* necessary information?
3. **Faithfulness:** Is the LLM's answer actually derived from the context, or is it hallucinating?
4. **Answer Relevance:** Does the answer address the user's question?
I would build a golden dataset of Q&A pairs and run automated evaluations on every pipeline update.

## Interviewer Feedback
* **Score:** 4/5 (Strong Hire)
* **Strengths:** 
    * Clear architecture separation (ingestion vs. inference).
    * Highlighted crucial enterprise concerns like metadata filtering for RBAC (Role-Based Access Control).
    * Addressed conversational memory natively.
    * Proposed a modern, industry-standard evaluation framework (RAGAS).
* **Areas for Improvement:** 
    * Could have discussed advanced retrieval techniques like hybrid search (keyword + vector) or re-ranking to improve context precision.

## Improved Answer
Candidate could add: "To improve retrieval quality, especially for specific acronyms or employee names, I would implement Hybrid Search—combining dense vector search with sparse keyword search (BM25). Furthermore, I'd retrieve a larger number of documents (e.g., top 20) and use a cross-encoder Re-ranker (like Cohere Rerank) to narrow it down to the top 5 before passing to the LLM."

## Hiring Manager Notes
Candidate has practical, hands-on knowledge of modern AI stacks, not just theoretical ML. Security awareness is a huge plus. Hire.
