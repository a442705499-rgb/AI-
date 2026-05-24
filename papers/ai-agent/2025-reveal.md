# ReVeal: Self-Evolving Code Agents via Reliable Self-Verification

## Basic Info

- Paper: ReVeal: Self-Evolving Code Agents via Reliable Self-Verification
- Authors: Yiyang Jin, Kunzhao Xu, Hang Li, Xueting Han, Yanmin Zhou, Cheng Li, Jing Bai
- Institution: Microsoft
- Year: 2025
- arXiv: https://arxiv.org/abs/2506.11442
- OpenReview: https://openreview.net/forum?id=q56ZI1Co43
- Tags: code agents, self-verification, RLVR, test-time scaling, tool feedback, TAPO

## One-Sentence Summary

ReVeal trains code agents to improve through iterative generation and reliable self-verification, allowing them to construct tests, use tool feedback, and refine solutions over many turns.

## Motivation

Reinforcement learning with verifiable rewards has improved reasoning models, but many methods mainly optimize final outcome rewards. For coding agents, this is not enough: the model must also learn to verify its own solution, generate useful tests, interpret tool feedback, and decide how to revise code.

The paper focuses on a key asymmetry: code generation and code verification are different skills, and verification can guide deeper test-time scaling if it becomes reliable.

## Core Idea

ReVeal structures code solving as an iterative generation-verification loop.

At each turn, the agent can:

- generate or revise code
- construct verification tests
- run tool-based feedback
- inspect failures
- update the solution

The framework explicitly optimizes self-verification so the model can better use its own tests and tool results during long-horizon coding tasks.

## Method Details

### 1. Iterative Generation-Verification

Instead of producing one final answer, the agent alternates between code generation and verification. This creates a multi-turn trajectory where verification quality directly affects future generation quality.

### 2. Reliable Self-Verification

The model is trained to produce more useful verification signals, such as test cases and feedback interpretation. This widens the verification-generation gap in a positive way: stronger verification creates better pressure for generation improvement.

### 3. Tool-Based Evaluation

The agent uses a Python interpreter or execution environment to test candidate code. Tool feedback provides grounded signals that are more reliable than pure self-critique.

### 4. TAPO for Turn-Level Credit Assignment

ReVeal incorporates TAPO to assign rewards at the turn level. This matters because long coding trajectories contain multiple intermediate decisions, and final outcome rewards alone are too sparse.

## Experiments

The paper evaluates ReVeal on coding benchmarks including LiveCodeBench.

Reported findings include:

- ReVeal improves Pass@k, showing stronger exploration over candidate solutions.
- Models trained for only a few turns can continue improving for 20+ inference turns.
- Verification accuracy improves faster than generation accuracy, enabling more effective test-time scaling.

## Strengths

- Treats verification as a first-class trainable capability instead of a passive final check.
- Uses execution feedback, which is more grounded than language-only self-reflection.
- Supports long-horizon coding behavior through iterative generation and verification.
- Turn-level credit assignment provides denser learning signals than final outcome reward alone.
- The method connects RL training with practical coding-agent workflows.

## Limitations

- Tool feedback quality depends on the execution environment and generated tests.
- Self-generated tests may still be incomplete or biased toward the model's current hypothesis.
- Long inference trajectories increase latency and compute cost.
- The method is most natural for tasks with executable verification; it may transfer less directly to non-code reasoning tasks.

## Engineering Takeaways

- Coding agents should learn to verify, not just generate.
- Execution feedback is a powerful reward source when it is integrated into the reasoning loop.
- Test-time scaling can come from better intermediate verification, not only from sampling more final answers.
- Reward design for code agents should include turn-level signals such as test quality, failure interpretation, and revision effectiveness.
- Multi-turn code agents need memory over failed attempts, generated tests, and tool outputs.

## Reproduction Plan

1. Choose a small set of programming problems with executable unit tests.
2. Build an agent loop with code generation, test generation, execution, and revision.
3. Track per-turn outputs: code, tests, tool feedback, and revision decisions.
4. Use final correctness plus intermediate verification quality as rewards.
5. Compare single-shot coding, self-reflection, and iterative generation-verification.

## Interview Notes

ReVeal is important because it treats self-verification as an optimizable capability. For code agents, the ability to generate tests, use tool feedback, and revise over many turns can be more valuable than simply producing one stronger first answer.
