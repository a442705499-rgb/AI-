# Language Models are Few-Shot Learners

## Basic Info

- Paper: Language Models are Few-Shot Learners
- Authors: Tom B. Brown et al.
- Venue / Year: NeurIPS 2020
- Link: https://arxiv.org/abs/2005.14165
- Tags: GPT-3, scaling laws, in-context learning, few-shot prompting

## One-Sentence Summary

GPT-3 demonstrates that sufficiently large autoregressive language models can perform many tasks from natural-language prompts and a few examples without gradient-based fine-tuning.

## Core Idea

The paper scales an autoregressive Transformer to 175B parameters and evaluates it under zero-shot, one-shot, and few-shot prompting. The model learns to adapt behavior from context alone, revealing in-context learning as an emergent capability of large language models.

## Why It Matters

- Popularizes prompting as a model interaction paradigm.
- Shows that scale can unlock broad task generalization.
- Changes how language models are evaluated and deployed.

## Engineering Takeaways

- Prompt format becomes part of the application interface.
- Few-shot examples can guide model behavior without updating weights.
- Scaling increases capability but also raises cost, latency, and reliability challenges.

## Reproduction Plan

Evaluate a smaller autoregressive model on zero-shot and few-shot classification prompts, then compare how prompt examples affect accuracy and error patterns.
