# Direct Preference Optimization: Your Language Model is Secretly a Reward Model

## Basic Info

- Paper: Direct Preference Optimization: Your Language Model is Secretly a Reward Model
- Authors: Rafael Rafailov et al.
- Venue / Year: NeurIPS 2023
- Link: https://arxiv.org/abs/2305.18290
- Tags: preference optimization, alignment, RLHF alternative, policy optimization

## One-Sentence Summary

DPO optimizes language models directly from preference data without training an explicit reward model or running online RL.

## Core Idea

The paper derives a direct objective from the RLHF formulation. Instead of learning a reward model and optimizing with PPO, DPO trains the policy to increase likelihood of preferred responses and decrease likelihood of rejected responses relative to a reference model.

## Why It Matters

- Simplifies preference alignment pipelines.
- Reduces engineering complexity compared with PPO-based RLHF.
- Becomes a standard baseline for post-training language models.

## Engineering Takeaways

- Preference optimization can be implemented as supervised-style training.
- Reference models help constrain policy drift.
- Dataset quality and preference distribution still dominate final behavior.

## Reproduction Plan

Fine-tune a small language model with paired preferred/rejected responses using DPO, then compare it with supervised fine-tuning on the same task.
