# Measuring Massive Multitask Language Understanding

## Basic Info

- Paper: Measuring Massive Multitask Language Understanding
- Authors: Dan Hendrycks et al.
- Venue / Year: ICLR 2021
- Link: https://arxiv.org/abs/2009.03300
- Tags: MMLU, benchmark, multitask evaluation, knowledge assessment

## One-Sentence Summary

MMLU evaluates language models across a broad set of academic and professional subjects to measure multitask knowledge and reasoning.

## Core Idea

The benchmark contains multiple-choice questions from many domains, including STEM, humanities, social sciences, and professional exams. It tests whether models can generalize beyond narrow task-specific datasets.

## Why It Matters

- Becomes one of the most widely reported LLM evaluation benchmarks.
- Pushes evaluation toward broad knowledge and reasoning coverage.
- Reveals gaps between narrow benchmark performance and general capability.

## Engineering Takeaways

- Benchmark diversity matters for measuring general-purpose models.
- Few-shot prompt format can significantly affect scores.
- Aggregate scores should be broken down by domain to find weaknesses.

## Reproduction Plan

Run a small language model on selected MMLU subsets with zero-shot and few-shot prompts, then analyze domain-level strengths and failures.
