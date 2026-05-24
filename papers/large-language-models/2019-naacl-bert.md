# BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding

## Basic Info

- Paper: BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding
- Authors: Jacob Devlin, Ming-Wei Chang, Kenton Lee, Kristina Toutanova
- Venue / Year: NAACL 2019
- Link: https://arxiv.org/abs/1810.04805
- Tags: bidirectional pretraining, masked language modeling, representation learning

## One-Sentence Summary

BERT shows that deep bidirectional Transformer pretraining with masked language modeling can produce strong general-purpose language representations for many NLP tasks.

## Core Idea

Instead of training a left-to-right language model, BERT masks some input tokens and trains the model to reconstruct them using both left and right context. This produces bidirectional contextual representations that transfer well to classification, QA, and sequence labeling tasks.

## Why It Matters

- Establishes pretraining plus task-specific fine-tuning as a dominant NLP paradigm.
- Demonstrates the effectiveness of masked language modeling.
- Provides a reusable encoder backbone for language understanding.

## Engineering Takeaways

- Pretraining objectives shape downstream model behavior.
- Encoder-only models are still highly useful for embeddings, reranking, and classification.
- Fine-tuning can adapt a general pretrained model to many specialized tasks with limited data.

## Reproduction Plan

Train a small BERT-style encoder on a toy masked language modeling corpus, then fine-tune it on a sentence classification dataset to observe transfer from pretraining to downstream tasks.
