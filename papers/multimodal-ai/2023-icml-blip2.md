# BLIP-2: Bootstrapping Language-Image Pre-training with Frozen Image Encoders and Large Language Models

## Basic Info

- Paper: BLIP-2: Bootstrapping Language-Image Pre-training with Frozen Image Encoders and Large Language Models
- Authors: Junnan Li et al.
- Venue / Year: ICML 2023
- Link: https://arxiv.org/abs/2301.12597
- Tags: BLIP-2, Q-Former, vision-language pretraining, frozen LLMs

## One-Sentence Summary

BLIP-2 uses a lightweight Q-Former to connect frozen vision encoders with frozen large language models, enabling efficient vision-language pretraining.

## Core Idea

The Q-Former learns a compact set of query embeddings that extract useful visual information and pass it into a language model. By freezing the heavy vision and language backbones, BLIP-2 reduces training cost while preserving strong pretrained capabilities.

## Why It Matters

- Provides an efficient recipe for building vision-language models from frozen components.
- Introduces Q-Former as a reusable visual information bottleneck.
- Influences many later multimodal LLM systems.

## Engineering Takeaways

- Lightweight connector modules can be more practical than full-model retraining.
- Frozen backbones reduce compute cost and simplify training.
- Visual token compression is important for multimodal inference efficiency.

## Reproduction Plan

Freeze a vision encoder and a small language model, train a lightweight query module on image-caption data, and evaluate captioning or visual QA performance.
