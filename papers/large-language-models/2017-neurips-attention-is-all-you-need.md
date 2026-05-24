# Attention Is All You Need

## Basic Info

- Paper: Attention Is All You Need
- Authors: Ashish Vaswani et al.
- Venue / Year: NeurIPS 2017
- Link: https://arxiv.org/abs/1706.03762
- Tags: Transformer, self-attention, sequence modeling, LLM foundations

## One-Sentence Summary

This paper introduces the Transformer, a sequence model based entirely on self-attention and feed-forward layers, removing recurrence and convolution from the core architecture.

## Core Idea

The Transformer replaces recurrent sequence processing with multi-head self-attention, allowing every token to directly attend to every other token. This design improves parallelism, captures long-range dependencies more effectively, and becomes the architectural foundation of modern large language models.

## Why It Matters

- Defines the core architecture behind GPT, BERT, T5, LLaMA, and most modern LLMs.
- Makes large-scale parallel training practical.
- Establishes attention as a general mechanism for token interaction.

## Engineering Takeaways

- Self-attention is a flexible routing mechanism over tokens.
- Positional encoding is required because the architecture has no recurrence.
- Multi-head attention gives the model multiple representation subspaces.
- Scaling Transformer blocks is the central engineering path behind modern LLMs.

## Reproduction Plan

Implement a minimal Transformer encoder-decoder with multi-head attention, residual connections, layer normalization, and positional encoding. Train it on a toy translation or sequence-copying task to verify the architecture.
