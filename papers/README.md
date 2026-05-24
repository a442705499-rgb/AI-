# Paper Reading Notes

This folder tracks AI papers by research direction. The taxonomy mirrors the repository focus areas so the reading log stays easy to browse as it grows.

## Directory Map

| Direction | Folder | Focus |
| --- | --- | --- |
| Large Language Models | [large-language-models/](large-language-models/) | Transformer, instruction tuning, alignment, long-context modeling, reasoning |
| RAG | [rag/](rag/) | RAG, GraphRAG, retrieval, reranking, evidence aggregation |
| AI Agent | [ai-agent/](ai-agent/) | agent workflows, tool use, coding agents, self-verification, memory |
| Multimodal AI | [multimodal-ai/](multimodal-ai/) | VLMs, image-text alignment, multimodal reasoning |
| Efficient AI | [efficient-ai/](efficient-ai/) | LoRA, QLoRA, quantization, distillation, efficient inference |
| Evaluation | [evaluation/](evaluation/) | benchmarks, hallucination analysis, ablations, production metrics |
| Agentic RL | [agentic-rl/](agentic-rl/) | RL for LLM agents, multi-agent RL, credit assignment, long-horizon training |

## Reading Log

| Date | Paper | Venue / Year | Area | Status |
| --- | --- | --- | --- | --- |
| 2026-05-24 | [LinearRAG: Linear Graph Retrieval Augmented Generation on Large-scale Corpora](rag/2026-iclr-linearrag.md) | ICLR 2026 Poster | RAG / GraphRAG | Summarized |
| 2026-05-24 | [Stronger-MAS: Multi-Agent Reinforcement Learning for Collaborative LLMs](agentic-rl/2026-iclr-stronger-mas.md) | ICLR 2026 | Agentic RL / Multi-Agent Systems | Summarized |
| 2026-05-24 | [Agent Lightning: Train ANY AI Agents with Reinforcement Learning](agentic-rl/2025-agent-lightning.md) | arXiv 2025 | Agentic RL / Decoupled Training | Summarized |
| 2026-05-24 | [ReVeal: Self-Evolving Code Agents via Reliable Self-Verification](ai-agent/2025-reveal.md) | arXiv 2025 / ICLR 2026 | AI Agent / Code Agents | Summarized |

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
