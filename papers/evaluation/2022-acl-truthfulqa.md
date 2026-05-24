# TruthfulQA: Measuring How Models Mimic Human Falsehoods

## Basic Info

- Paper: TruthfulQA: Measuring How Models Mimic Human Falsehoods
- Authors: Stephanie Lin, Jacob Hilton, Owain Evans
- Venue / Year: ACL 2022
- Link: https://arxiv.org/abs/2109.07958
- Tags: truthfulness, hallucination, benchmark, model evaluation

## One-Sentence Summary

TruthfulQA evaluates whether language models generate truthful answers or repeat common human misconceptions.

## Core Idea

The benchmark asks questions where many humans would answer falsely due to misconceptions. It measures whether models reproduce those falsehoods or provide truthful, grounded answers.

## Why It Matters

- Highlights truthfulness as distinct from fluency and popularity.
- Shows that larger models can still imitate false beliefs.
- Influences later hallucination and factuality evaluation.

## Engineering Takeaways

- High-quality generation is not the same as truthful generation.
- Evaluation sets should include adversarial and misconception-heavy prompts.
- Factuality metrics need human or model-assisted judgment beyond exact match.

## Reproduction Plan

Evaluate a model on a subset of TruthfulQA, categorize failures by misconception type, and compare direct answering with retrieval-augmented answering.
