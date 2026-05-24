# ReAct: Synergizing Reasoning and Acting in Language Models

## Basic Info

- Paper: ReAct: Synergizing Reasoning and Acting in Language Models
- Authors: Shunyu Yao et al.
- Venue / Year: ICLR 2023
- Link: https://arxiv.org/abs/2210.03629
- Tags: AI agents, reasoning, acting, tool use, prompting

## One-Sentence Summary

ReAct interleaves reasoning traces and environment actions, enabling language models to plan, call tools, observe results, and update their reasoning loop.

## Core Idea

The method prompts an LLM to alternate between reasoning and acting. Reasoning steps help the model maintain task state, while actions interact with external tools or environments. Observations from the environment then guide the next reasoning step.

## Why It Matters

- Establishes a simple and influential pattern for tool-using agents.
- Makes agent behavior more interpretable through explicit reasoning traces.
- Connects language reasoning with environment feedback.

## Engineering Takeaways

- Agent loops need structured action-observation traces.
- Tool results should be fed back into the reasoning context.
- Prompt format can define an effective agent policy without training.

## Reproduction Plan

Implement a ReAct-style loop for a search QA task using `Thought`, `Action`, and `Observation` fields, then compare it with direct answer generation.
