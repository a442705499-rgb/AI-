# Stronger-MAS: Multi-Agent Reinforcement Learning for Collaborative LLMs

## Basic Info

- Paper: Stronger-MAS: Multi-Agent Reinforcement Learning for Collaborative LLMs
- Authors: Yujie Zhao, Lanxiang Hu, Yang Wang, Minmin Hou, Hao Zhang, Ke Ding, Jishen Zhao
- Venue / Year: ICLR 2026
- arXiv: https://arxiv.org/abs/2510.11062
- OpenReview: https://openreview.net/forum?id=IdF6JqXWzx
- Code: https://github.com/zoeyuchao/Stronger-MAS
- Tags: multi-agent systems, agent RL, GRPO, collaborative LLMs, long-horizon planning

## One-Sentence Summary

Stronger-MAS introduces AT-GRPO, an agent- and turn-wise grouped RL method that trains collaborative LLM agent teams more effectively than standard single-agent GRPO-style optimization.

## Motivation

Multi-agent systems improve LLM agents by assigning roles, dividing work, and coordinating multiple reasoning paths. Reinforcement learning can further improve agent policies through environmental rewards. However, applying on-policy RL to multi-agent systems is difficult because standard GRPO assumes grouped responses for the same prompt, while MAS rollouts contain different agents, roles, prompts, and turns.

The paper targets a practical gap: how to train a team of LLM agents with RL while preserving role specialization, collaboration, and long-horizon interaction structure.

## Core Idea

The key contribution is AT-GRPO, short for agent- and turn-wise grouped GRPO.

Instead of grouping all responses as if they came from a single prompt distribution, AT-GRPO groups rollouts by agent role and interaction turn. This makes the policy-gradient signal better aligned with multi-agent collaboration, because each agent is optimized in the context of its own role, state, and turn-level responsibility.

The paper also builds a training system that supports both:

- single-policy MAS, where all agents share one model
- multi-policy MAS, where agents can use separate policies

## Method Details

### 1. MAS Rollout Structure

The training system collects complete multi-agent trajectories from task environments. Each trajectory includes agent identities, turn indices, prompts, actions, observations, and final rewards.

### 2. Agent- and Turn-Wise Grouping

AT-GRPO computes grouped baselines and advantages at the agent-turn level. This avoids mixing incompatible samples across different roles and turns.

### 3. Collaborative Policy Optimization

The optimization objective improves the policy while preserving the structure of team interaction. The method is designed for game, planning, coding, and math tasks where agents must coordinate over multiple turns.

### 4. Single-Policy and Multi-Policy Training

The framework supports both shared-model and role-specific-model training. This matters because some MAS designs rely on one generalist model, while others benefit from specialized agents.

## Experiments

The paper evaluates Stronger-MAS across game, planning, coding, and math tasks.

Reported highlights include:

- Long-horizon planning accuracy improves from a 14.0%-47.0% single-agent RL baseline to 96.0%-99.5%.
- Coding tasks improve by 3.87%-7.62% on average.
- Math tasks improve by 9.0%-17.93%.

The results suggest that team-level RL can produce stronger division of labor, better coordination, and more stable long-horizon behavior than directly applying single-agent RL.

## Strengths

- Directly addresses the mismatch between standard GRPO and multi-agent trajectories.
- Makes role and turn structure part of the RL grouping logic.
- Supports both shared-policy and multi-policy agent teams.
- Shows large gains on long-horizon planning, where collaboration quality matters most.
- Provides a useful recipe for training agents that must specialize and coordinate over time.

## Limitations

- Multi-agent RL systems are more complex to implement and debug than single-agent training loops.
- Reward design remains task-dependent, especially for open-ended collaboration.
- Scaling to many heterogeneous agents may increase rollout cost and training instability.
- The paper focuses on benchmark tasks; production deployment would require safety, observability, and failure recovery analysis.

## Engineering Takeaways

- Multi-agent training should preserve role and turn information instead of flattening all actions into one generic trajectory.
- Grouped RL baselines must match the structure of the agent workflow.
- Long-horizon planning benefits from team training because different agents can develop complementary behaviors.
- MAS training infrastructure should treat trajectories as structured interaction graphs, not just text sequences.

## Reproduction Plan

1. Start with a simple two-agent planning environment.
2. Record trajectories with agent ID, turn ID, prompt, action, observation, and reward.
3. Implement a simplified grouped advantage estimator by agent and turn.
4. Compare standard GRPO-style grouping with AT-GRPO-style grouping.
5. Evaluate planning accuracy, coordination failures, and rollout length.

## Interview Notes

Stronger-MAS is important because it points out that agentic RL is not just "RL on longer text." Multi-agent rollouts have structure: roles, turns, partial observations, and coordination dependencies. AT-GRPO improves training by aligning the RL grouping mechanism with that structure.
