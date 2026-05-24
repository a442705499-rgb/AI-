# Training Language Models to Follow Instructions with Human Feedback

## Basic Info

- Paper: Training Language Models to Follow Instructions with Human Feedback
- Authors: Long Ouyang et al.
- Venue / Year: NeurIPS 2022
- Link: https://arxiv.org/abs/2203.02155
- Tags: RLHF, instruction following, reward models, alignment

## One-Sentence Summary

This paper trains language models to better follow user instructions by combining supervised fine-tuning, reward modeling, and reinforcement learning from human feedback.

## Core Idea

The method collects human demonstrations and preference comparisons, trains a reward model from preferences, then optimizes the policy with reinforcement learning. The resulting model better aligns with human preferences than a purely pretrained model.

## Why It Matters

- Establishes the RLHF pipeline behind instruction-following assistants.
- Shows that human preference optimization can improve usability.
- Provides the foundation for later agentic alignment and policy optimization methods.

## Engineering Takeaways

- Reward data quality is central to model behavior.
- RL optimization can improve helpfulness but requires careful stability control.
- Alignment pipelines combine data, modeling, and optimization rather than a single algorithm.

## Reproduction Plan

Build a toy RLHF pipeline with preference pairs, a small reward model, and policy optimization on a constrained instruction-following task.
