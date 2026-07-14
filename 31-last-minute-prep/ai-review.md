# AI & ML Engineering Quick Reference

## Core Concepts
*   **Supervised Learning:** Training data includes labels (e.g., Classification, Regression).
*   **Unsupervised Learning:** Training data is unlabeled (e.g., Clustering, Dimensionality Reduction).
*   **Reinforcement Learning:** Agent learns by interacting with an environment to maximize a reward.
*   **Embeddings:** Representing words, images, or data as dense vectors in a continuous space. Similar concepts have high cosine similarity.

## LLMs & Generative AI
*   **Transformer Architecture:** Based on the "Attention is All You Need" paper. Processes input in parallel rather than sequentially (like RNNs).
*   **Self-Attention:** Mechanism allowing the model to weigh the importance of different words in a sequence relative to each other.
*   **Tokens:** The basic unit of data processed by an LLM (words, parts of words, or characters).
*   **Context Window:** The maximum number of tokens a model can process (input + output) in a single request.
*   **RAG (Retrieval-Augmented Generation):** Enhancing LLM responses by retrieving relevant information from an external database (often a Vector DB) and injecting it into the prompt.

## Model Evaluation Metrics
*   **Classification:**
    *   *Accuracy:* Total correct / Total predictions. (Misleading on imbalanced datasets).
    *   *Precision:* True Positives / (True Positives + False Positives). (Minimizing false alarms).
    *   *Recall:* True Positives / (True Positives + False Negatives). (Capturing all real instances).
    *   *F1 Score:* Harmonic mean of Precision and Recall.
*   **LLMs:**
    *   *Perplexity:* How well a probability model predicts a sample. Lower is better.
    *   *BLEU/ROUGE:* Primarily for translation/summarization. Overlap of n-grams with reference text.

## Prompt Engineering Techniques
*   **Zero-Shot:** Asking a task without providing examples.
*   **Few-Shot:** Providing 2-3 examples of the desired input/output format.
*   **Chain of Thought (CoT):** Appending "Let's think step by step" to force the model to break down reasoning, significantly improving logic tasks.
