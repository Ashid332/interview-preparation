# AI Engineer Interview Learning Path

## Role Overview
AI Engineers specialize in building applications on top of large language models (LLMs) and other AI primitives. This is an emerging, fast-paced role that blends software engineering, prompt engineering, search architectures (RAG), and API integrations. This 8-week path prepares you to build, evaluate, and scale AI-powered applications.

## Prerequisites

| Skill Area | Expected Proficiency Level | Resources for Review |
|------------|----------------------------|----------------------|
| Programming | Advanced (Python or TypeScript) | Python/TS docs |
| APIs & SDKs | Intermediate | REST concepts, HTTP clients |
| Basic ML Concepts | Beginner/Intermediate | OpenAI API Documentation |

## Path Overview

```mermaid
gantt
    title AI Engineer 8-Week Preparation Plan
    dateFormat  w
    axisFormat %W
    section Fundamentals
    Prompts & LLMs        :a1, 0, 2w
    section Architectures
    RAG & Agents          :a2, after a1, 3w
    section Deployment & Eval
    Evals & MLOps Lite    :a3, after a2, 2w
    section Interview Prep
    Mock Interviews       :a4, after a3, 1w
```

## Weekly Roadmap

### Weeks 1-2: Prompt Engineering & API Mastery
Understanding the core capabilities and limitations of foundational models.

| Week | Focus Area | Key Concepts | Practice Goal |
|------|------------|--------------|---------------|
| 1 | Prompt Engineering | Few-shot, Chain-of-Thought, System Prompts, JSON output | Build a CLI tool for text summarization/classification |
| 2 | LLM APIs & Ecosystem | OpenAI/Anthropic APIs, Temperature, Top-P, Streaming | Implement a streaming chat interface |

### Weeks 3-5: RAG & AI Architectures
Building context-aware applications that utilize external data.

| Week | Focus Area | Key Concepts | Practice Goal |
|------|------------|--------------|---------------|
| 3 | Embeddings & Vector DBs | Vector Math, Cosine Similarity, Pinecone/Chroma/Weaviate | Build a semantic search engine over technical docs |
| 4 | RAG Pipelines | Retrieval-Augmented Generation, Chunking strategies, Re-ranking | Build a "Chat with your PDF" application |
| 5 | Agents & Tool Use | Function Calling, LangChain, LlamaIndex, ReAct pattern | Build an agent that can query a SQL database |

### Weeks 6-7: Evaluation, Safety & Scaling
Moving from prototype to production.

| Week | Focus Area | Key Concepts | Action Item |
|------|------------|--------------|-------------|
| 6 | Evaluations & Metrics | LLM-as-a-judge, RAGAS, BLEU/ROUGE, Ground truth datasets | Set up an automated evaluation pipeline for your RAG app |
| 7 | Safety & Prompt Injection | Jailbreaks, Guardrails, Output parsing validation | Implement input/output sanitization filters |

### Week 8: Behavioral & System Design
Finalizing readiness for the AI engineering interview loop.

| Week | Focus Area | Key Concepts | Action Item |
|------|------------|--------------|-------------|
| 8 | AI System Design & Mocks | Scalable AI architectures, Cost optimization, Latency | Design a scalable Customer Support Chatbot |

## Milestones & Checkpoints

- [ ] **End of Week 2:** Can effectively wrangle structured data (JSON) out of an LLM consistently.
- [ ] **End of Week 5:** Have built a working RAG pipeline from scratch without relying on heavy frameworks (like Langchain).
- [ ] **End of Week 7:** Understand how to quantitatively measure if a prompt change actually improved the output.
- [ ] **End of Week 8:** Can whiteboard an AI application architecture, detailing vector store choices and caching strategies.

## Company Recommendations

- **AI Native Startups (Jasper, Copy.ai, Harvey):** Deep focus on prompt hacking, latest models (Llama 3, GPT-4o), and rapid prototyping.
- **Enterprise Tech (Notion, Salesforce):** Focus on safety, deterministic outputs, data privacy, and scale.
- **Consultancies:** Broad knowledge of different model providers (Azure OpenAI, AWS Bedrock) and integration patterns.

## Interview Readiness Checklist

- [ ] Understand the nuances of different chunking strategies for RAG.
- [ ] Can articulate the trade-offs between Fine-tuning vs RAG.
- [ ] Comfortable discussing how to handle LLM hallucinations and rate limits.
- [ ] Have 3+ STAR stories discussing building and debugging AI features.
