# LoRA: Low-Rank Adaptation of Large Language Models

## Basic Info

- Paper: LoRA: Low-Rank Adaptation of Large Language Models
- Authors: Edward J. Hu et al.
- Venue / Year: ICLR 2022
- Link: https://arxiv.org/abs/2106.09685
- Tags: parameter-efficient fine-tuning, low-rank adaptation, LLM training

## One-Sentence Summary

LoRA fine-tunes large models by learning low-rank update matrices while keeping the original model weights frozen.

## Core Idea

Instead of updating all parameters, LoRA injects trainable low-rank matrices into selected layers. The low-rank updates approximate task-specific weight changes with far fewer trainable parameters.

## Why It Matters

- Makes fine-tuning large models cheaper and easier to store.
- Enables multi-task adaptation with small adapter weights.
- Becomes a standard method for LLM customization.

## Engineering Takeaways

- Most fine-tuning updates can be represented in a low-rank subspace.
- Adapter weights are easy to save, share, and merge.
- Choosing target modules and rank strongly affects performance and cost.

## Reproduction Plan

Apply LoRA to attention projection layers of a small Transformer and compare trainable parameter count, memory usage, and validation performance against full fine-tuning.
