# Learning Transferable Visual Models From Natural Language Supervision

## Basic Info

- Paper: Learning Transferable Visual Models From Natural Language Supervision
- Authors: Alec Radford et al.
- Venue / Year: ICML 2021
- Link: https://arxiv.org/abs/2103.00020
- Tags: CLIP, contrastive learning, vision-language models, zero-shot transfer

## One-Sentence Summary

CLIP learns aligned image and text representations from large-scale natural-language supervision, enabling strong zero-shot image classification.

## Core Idea

The model trains an image encoder and a text encoder with a contrastive objective. Matching image-text pairs are pulled together in embedding space, while mismatched pairs are pushed apart. At inference time, classification becomes image-text similarity matching.

## Why It Matters

- Establishes contrastive image-text pretraining as a foundation for multimodal AI.
- Enables zero-shot transfer to many vision tasks.
- Provides reusable representations for retrieval, classification, and multimodal agents.

## Engineering Takeaways

- Natural-language supervision can scale visual representation learning.
- Prompt design affects zero-shot classification performance.
- Embedding alignment enables flexible cross-modal retrieval.

## Reproduction Plan

Train a small image-text contrastive model on a toy paired dataset, then evaluate zero-shot classification with text prompts.
