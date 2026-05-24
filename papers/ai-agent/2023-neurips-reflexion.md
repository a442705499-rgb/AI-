# Reflexion: Language Agents with Verbal Reinforcement Learning

## Basic Info

- Paper: Reflexion: Language Agents with Verbal Reinforcement Learning
- Authors: Noah Shinn et al.
- Venue / Year: NeurIPS 2023
- Link: https://arxiv.org/abs/2303.11366
- Tags: AI agents, verbal feedback, memory, self-improvement

## One-Sentence Summary

Reflexion improves language agents by storing verbal feedback from past failures and using it as memory for future attempts.

## Core Idea

After each episode, the agent reflects on the outcome and writes a natural-language lesson into memory. Future attempts retrieve this memory and use it to avoid repeated mistakes, forming a lightweight self-improvement loop without parameter updates.

## Why It Matters

- Shows that agent learning can happen through memory and reflection, not only gradient updates.
- Provides a practical approach for improving agents in sparse-reward environments.
- Influences later work on agent memory, self-correction, and iterative problem solving.

## Engineering Takeaways

- Memory should store failure modes and corrective strategies, not just raw traces.
- Verbal feedback can be a useful intermediate representation for agent improvement.
- Reflection quality strongly affects long-horizon agent reliability.

## Reproduction Plan

Build an agent for a small coding or web-navigation task, store natural-language reflections after failed attempts, and measure whether retrieved reflections improve future success rates.
