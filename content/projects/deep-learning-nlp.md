---
title: "Deep Learning for Scientific Text Classification"
date: 2025-06-10
description: "Fine-tuning transformer models to classify research papers by domain and methodology."
tags: ["NLP", "Deep Learning", "Transformers", "Python"]
categories: ["AI"]
summary: "Fine-tuned SciBERT to automatically classify 50k+ research abstracts by discipline and methodology type."
ShowToc: true
---

## Overview

This project tackles the challenge of **automatically categorizing large volumes of scientific literature**. By fine-tuning a domain-specific transformer model (SciBERT), the system classifies research paper abstracts into discipline (e.g., physics, biology, CS) and methodology (experimental, theoretical, computational).

## Motivation

Researchers and institutions face an overwhelming volume of published papers. Automated classification helps with literature reviews, trend analysis, and building curated reading lists.

## Technical Approach

1. **Dataset** — 50,000 abstracts from Semantic Scholar, annotated with discipline and methodology labels.
2. **Model** — SciBERT (`allenai/scibert_scivocab_uncased`), a BERT variant pre-trained on scientific text.
3. **Fine-Tuning** — Multi-label classification head; trained with weighted cross-entropy to handle class imbalance.
4. **Evaluation** — 5-fold cross-validation with macro F1 as the primary metric.

## Key Results

| Metric | Score |
|---|---|
| Macro F1 (discipline) | 0.91 |
| Macro F1 (methodology) | 0.87 |
| Inference latency | 12 ms / abstract (GPU) |

## Technologies

- **PyTorch** + **Hugging Face Transformers**
- **SciBERT** pre-trained model
- **Weights & Biases** for experiment tracking
- **Python**, **pandas**, **scikit-learn**

## Links

- 📂 [GitHub Repository](https://github.com/yourusername/scitext-classifier)
- 📄 [Conference Paper (arXiv)](#)
