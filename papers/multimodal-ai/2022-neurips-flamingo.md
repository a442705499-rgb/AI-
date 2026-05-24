# Flamingo: a Visual Language Model for Few-Shot Learning

## Basic Info

- Paper: Flamingo: a Visual Language Model for Few-Shot Learning
- Authors: Jean-Baptiste Alayrac et al.
- Venue / Year: NeurIPS 2022
- Link: https://arxiv.org/abs/2204.14198
- Tags: visual language model, few-shot learning, cross-attention, multimodal generation

## One-Sentence Summary

Flamingo connects pretrained vision encoders and language models with cross-attention layers to perform few-shot multimodal understanding and generation.

## Core Idea

The model keeps strong pretrained vision and language components, then adds gated cross-attention layers that allow the language model to condition on visual inputs. This enables flexible few-shot multimodal prompting.

## Why It Matters

- Shows how to adapt large language models into visual language models.
- Demonstrates strong few-shot performance across image and video tasks.
- Influences later multimodal assistant architectures.

## Engineering Takeaways

- Reusing pretrained unimodal models can reduce multimodal training cost.
- Cross-attention is a practical bridge between visual tokens and language tokens.
- Few-shot multimodal prompting requires careful input formatting.

## Reproduction Plan

Prototype a small vision-language model by freezing an image encoder and language model, then train lightweight cross-attention adapters on image-caption data.
