# Paper Reading Notes

This folder tracks AI papers by research direction. The goal is not only to collect papers, but to build a clear research-to-engineering workflow.

## Directory Map

| Direction | Folder | Focus |
| --- | --- | --- |
| RAG and Graph Retrieval | [rag/](rag/) | RAG, GraphRAG, retrieval, reranking, evidence aggregation |
| Agent RL | [agent-rl/](agent-rl/) | RL for LLM agents, multi-agent systems, long-horizon planning |
| Code Agents | [code-agents/](code-agents/) | coding agents, self-verification, tool feedback, test-time scaling |
| Multimodal AI | [multimodal/](multimodal/) | VLMs, image-text alignment, multimodal reasoning |
| Efficient AI | [efficient-ai/](efficient-ai/) | LoRA, QLoRA, quantization, distillation, efficient inference |
| Evaluation | [evaluation/](evaluation/) | benchmarks, hallucination analysis, ablations, production metrics |

## Reading Log

| Date | Paper | Venue / Year | Area | Status |
| --- | --- | --- | --- | --- |
| 2026-05-24 | [LinearRAG: Linear Graph Retrieval Augmented Generation on Large-scale Corpora](rag/2026-iclr-linearrag.md) | ICLR 2026 Poster | RAG / GraphRAG | Summarized |
| 2026-05-24 | [Stronger-MAS: Multi-Agent Reinforcement Learning for Collaborative LLMs](agent-rl/2026-iclr-stronger-mas.md) | ICLR 2026 | Agent RL / Multi-Agent Systems | Summarized |
| 2026-05-24 | [Agent Lightning: Train ANY AI Agents with Reinforcement Learning](agent-rl/2025-agent-lightning.md) | arXiv 2025 | Agent RL / Decoupled Training | Summarized |
| 2026-05-24 | [ReVeal: Self-Evolving Code Agents via Reliable Self-Verification](code-agents/2025-reveal.md) | arXiv 2025 / ICLR 2026 | Code Agents / RLVR | Summarized |

## Paper Note Format

Each paper note should answer these questions:

1. What problem does the paper solve?
2. What is the main idea?
3. What is the model architecture or algorithm?
4. What data and training setup are used?
5. What experiments prove the method works?
6. What are the limitations?
7. What can be reused in real projects?
8. How can I reproduce a minimal version?

Use [template.md](template.md) for every new paper.

## Upcoming Updates

New paper notes will be added under their research-direction folders so the repository stays easy to browse as the reading list grows.
