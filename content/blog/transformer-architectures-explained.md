---
title: "Transformer Architectures Explained Simply"
date: 2025-08-05
description: "A clear, visual walkthrough of how transformers work — attention, encoders, decoders, and why they changed AI."
tags: ["Deep Learning", "Transformers", "NLP", "AI"]
categories: ["Explainers"]
summary: "Demystifying transformer architectures — from self-attention to multi-head attention — with intuitive explanations and minimal math."
ShowToc: true
---

Transformers are the architecture behind GPT, BERT, and virtually every state-of-the-art model in NLP, vision, and beyond. Let's break down how they work.

## The Big Idea

Before transformers, models like RNNs and LSTMs processed sequences **one token at a time**. Transformers process the **entire sequence in parallel** using a mechanism called **self-attention**.

> **Self-attention** lets each word in a sentence "look at" every other word to determine context.

## Self-Attention in 3 Steps

For each token in the input:

1. **Query, Key, Value** — Multiply the token embedding by three learned weight matrices to get Q, K, and V vectors.
2. **Attention Scores** — Compute the dot product of Q with all K vectors, then apply softmax to get weights.
3. **Weighted Sum** — Multiply each V vector by its attention weight and sum to get the output.

```
Attention(Q, K, V) = softmax(Q · Kᵀ / √d_k) · V
```

The `√d_k` scaling prevents dot products from growing too large in high dimensions.

## Multi-Head Attention

Instead of computing attention once, transformers run **multiple attention heads in parallel**, each learning different relationship patterns (e.g., syntactic, semantic). The outputs are concatenated and linearly projected.

## Encoder vs. Decoder

| Component | Role | Example Models |
|---|---|---|
| **Encoder** | Reads and encodes the full input | BERT, RoBERTa |
| **Decoder** | Generates output, one token at a time | GPT-2, GPT-4 |
| **Encoder-Decoder** | Maps input sequence to output sequence | T5, BART |

## Positional Encoding

Since transformers process tokens in parallel (no inherent order), **positional encodings** are added to embeddings so the model knows the position of each token. Common approaches include sinusoidal functions and learned embeddings.

## Why Transformers Win

- **Parallelism** — Training is orders of magnitude faster than RNNs.
- **Long-range dependencies** — Attention connects any two positions directly.
- **Scalability** — Performance improves reliably with more data and parameters.

## Further Reading

- Vaswani et al., *"Attention Is All You Need"* (2017)
- Jay Alammar's [The Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/)
- Andrej Karpathy's [nanoGPT](https://github.com/karpathy/nanoGPT)

---

*If this was helpful, check out my other posts on deep learning fundamentals.*
