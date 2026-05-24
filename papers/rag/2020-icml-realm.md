# REALM: Retrieval-Augmented Language Model Pre-Training

## Basic Info

- Paper: REALM: Retrieval-Augmented Language Model Pre-Training
- Authors: Kelvin Guu, Kenton Lee, Zora Tung, Panupong Pasupat, Ming-Wei Chang
- Venue / Year: ICML 2020
- Link: https://arxiv.org/abs/2002.08909
- Tags: retrieval-augmented pretraining, open-domain QA, dense retrieval

## One-Sentence Summary

REALM integrates latent document retrieval into language model pretraining, allowing the model to learn how to retrieve and use external knowledge.

## Core Idea

Instead of only retrieving documents at inference time, REALM trains retrieval and language modeling together. The retriever selects documents that help predict masked tokens, and the language model learns to condition on retrieved evidence.

## Why It Matters

- Shows retrieval can be part of pretraining rather than a separate downstream module.
- Connects retrieval learning with language representation learning.
- Influences later retrieval-augmented pretraining and QA systems.

## Engineering Takeaways

- Jointly training retrieval and generation can improve evidence use.
- Retrieval indexes may need periodic refresh as representations change.
- End-to-end retrieval learning is powerful but operationally complex.

## Reproduction Plan

Train a small masked language model with a retrieval component over a tiny Wikipedia-style corpus, then compare masked-token prediction with and without retrieved evidence.
