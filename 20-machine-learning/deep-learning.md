# Deep Learning

## Overview
Deep Learning involves neural networks with multiple layers. Topics include architectures (CNNs, RNNs, Transformers), activation functions, backpropagation, optimization algorithms (Adam, SGD), and common issues like vanishing/exploding gradients.

## Interview Questions

### Q1: Explain the vanishing gradient problem and how to solve it.
**Difficulty:** Medium-Hard | **Frequency:** High | **Companies:** OpenAI, Google, Meta, Tesla

**Excellent Answer:**
The vanishing gradient problem occurs during backpropagation in deep neural networks. As errors are propagated backward from the output to the input layers, the gradients can become infinitesimally small. This happens because the chain rule multiplies multiple derivatives of the activation functions (like Sigmoid or Tanh), which have gradients between 0 and 1. As a result, early layers learn very slowly or not at all.
**Solutions:**
1. **Activation Functions:** Using ReLU or its variants (Leaky ReLU) since their derivative is 1 for positive inputs, preventing gradients from shrinking.
2. **Weight Initialization:** Using He or Xavier initialization to maintain the variance of activations and gradients across layers.
3. **Architecture:** Using Residual Networks (ResNets) with skip connections to allow gradients an alternate, direct path backward.
4. **Normalization:** Applying Batch Normalization to keep inputs to activation functions in a region where gradients are non-zero.

**Common Mistakes:**
- Confusing vanishing gradients with exploding gradients.
- Suggesting standardizing the input data as the primary fix (it helps with general optimization, but doesn't solve deep network vanishing gradients).

## Real-World Applications
- Computer Vision tasks like image segmentation (using CNNs).
- Natural Language Processing tasks like translation and summarization (using Transformers).

## Practice Problems

| Problem | Description | Difficulty | Link |
|---|---|---|---|
| Backpropagation | Manually calculate gradients for a 2-layer network | Hard | [Link](#) |
| CNN Architecture | Calculate the output dimensions of a Conv2D layer | Medium | [Link](#) |

## Hiring Manager Perspective
For specialized DL roles, we need deep mathematical intuition, not just the ability to write `import torch`. Candidates must understand the training dynamics, why a model isn't converging, and how to debug the architecture.

## AI Interview Coach
**ChatGPT/Claude/Gemini Prompts:**
- "Explain the self-attention mechanism in Transformers step-by-step."
- "Act as a strict technical interviewer and grill me on the differences between Adam and SGD with Momentum."
