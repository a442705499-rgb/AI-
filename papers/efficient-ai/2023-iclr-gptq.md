# GPTQ: Accurate Post-Training Quantization for Generative Pre-trained Transformers

## Basic Info

- Paper: GPTQ: Accurate Post-Training Quantization for Generative Pre-trained Transformers
- Authors: Elias Frantar et al.
- Venue / Year: ICLR 2023
- Link: https://arxiv.org/abs/2210.17323
- Tags: post-training quantization, LLM inference, compression

## One-Sentence Summary

GPTQ provides an efficient post-training quantization method that compresses large generative Transformers with limited accuracy loss.

## Core Idea

The method quantizes weights layer by layer while using second-order information to minimize reconstruction error. It avoids full retraining and focuses on practical compression for large pretrained models.

## Why It Matters

- Makes LLM inference more memory-efficient.
- Shows that strong post-training quantization is possible for very large Transformers.
- Influences later deployment stacks for quantized LLM serving.

## Engineering Takeaways

- Weight-only quantization can greatly reduce memory footprint.
- Calibration data and layer-wise error correction matter.
- Quantization should be evaluated on both perplexity and downstream tasks.

## Reproduction Plan

Apply a post-training quantization method to a small causal language model and compare model size, latency, perplexity, and answer quality before and after compression.
