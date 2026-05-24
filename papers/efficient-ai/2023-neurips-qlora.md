# QLoRA: Efficient Finetuning of Quantized LLMs

## Basic Info

- Paper: QLoRA: Efficient Finetuning of Quantized LLMs
- Authors: Tim Dettmers et al.
- Venue / Year: NeurIPS 2023
- Link: https://arxiv.org/abs/2305.14314
- Tags: quantization, LoRA, efficient fine-tuning, 4-bit training

## One-Sentence Summary

QLoRA enables high-quality fine-tuning of quantized LLMs by combining 4-bit base models with low-rank adapters.

## Core Idea

The method stores the pretrained model in 4-bit precision and backpropagates through it into LoRA adapters. It introduces NormalFloat4, double quantization, and paged optimizers to reduce memory while preserving fine-tuning quality.

## Why It Matters

- Makes fine-tuning large models feasible on much smaller hardware.
- Popularizes the practical stack of quantized base model plus LoRA adapters.
- Helps democratize instruction tuning and domain adaptation.

## Engineering Takeaways

- Quantization and parameter-efficient tuning compose well.
- Memory bottlenecks often matter more than raw compute in LLM fine-tuning.
- Evaluation must check whether compression changes downstream behavior.

## Reproduction Plan

Fine-tune a small open-source language model with LoRA and QLoRA, then compare memory usage, training speed, and task performance.
