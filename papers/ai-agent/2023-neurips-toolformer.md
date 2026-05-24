# Toolformer: Language Models Can Teach Themselves to Use Tools

## Basic Info

- Paper: Toolformer: Language Models Can Teach Themselves to Use Tools
- Authors: Timo Schick et al.
- Venue / Year: NeurIPS 2023
- Link: https://arxiv.org/abs/2302.04761
- Tags: tool use, self-supervised data generation, language agents

## One-Sentence Summary

Toolformer shows that language models can self-supervise tool-use examples and learn when and how to call external APIs.

## Core Idea

The model samples possible API calls in text, keeps the calls that improve language modeling likelihood, and fine-tunes on the filtered examples. This creates a training signal for tool use without requiring large manually annotated tool-call datasets.

## Why It Matters

- Makes tool use a learnable model behavior rather than only a prompt trick.
- Introduces a scalable data-generation approach for API calling.
- Helps define the boundary between language model capability and external computation.

## Engineering Takeaways

- Tool-call training data can be synthesized and filtered automatically.
- The decision of when to use a tool is as important as the tool output itself.
- Tool-using agents need a clear interface between natural language and API calls.

## Reproduction Plan

Create synthetic calculator or search API calls inside a small text corpus, filter calls that improve prediction quality, and fine-tune a small model on the retained examples.
