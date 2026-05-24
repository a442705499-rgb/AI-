# AI Frontier Lab

这里记录我对前沿 AI 技术、论文方法和工程实践的长期跟踪。内容会围绕大模型、RAG、多模态、模型高效训练与推理、AI Agent、评测体系等方向持续更新。

我更关注一件事：把论文里的关键思想拆开，看懂它为什么有效，再尽量转化成可复现、可解释、可落地的工程经验。

## Latest Paper Notes

| Paper | Venue | Direction | Key Idea |
| --- | --- | --- | --- |
| [LinearRAG: Linear Graph Retrieval Augmented Generation on Large-scale Corpora](papers/2026-iclr-linearrag.md) | ICLR 2026 Poster | GraphRAG / RAG | 用 relation-free Tri-Graph 替代不稳定的关系抽取，在大规模语料上实现线性复杂度、无额外 LLM token 的图检索增强生成 |

## What This Repository Shares

- 前沿 AI 论文精读：提炼问题背景、核心方法、实验设计和局限性
- 技术路线梳理：跟踪 LLM、RAG、Multimodal、Agent、Efficient AI 等方向的发展
- 工程复现笔记：把论文方法拆成模块，沉淀可运行的最小实现
- 实验与评测总结：记录数据、指标、消融、失败案例和改进方向
- 实用技术观察：关注新模型、新框架、新数据集和产业落地趋势

## Focus Areas

| Direction | Topics |
| --- | --- |
| Large Language Models | Transformer, instruction tuning, alignment, long-context modeling, reasoning, tool use |
| RAG | embeddings, chunking, vector search, reranking, hybrid retrieval, evaluation |
| AI Agent | planning, memory, tool calling, workflow orchestration, multi-agent systems |
| Multimodal AI | vision-language models, contrastive learning, image-text alignment, multimodal reasoning |
| Efficient AI | LoRA, QLoRA, distillation, quantization, pruning, KV cache, inference optimization |
| Evaluation | benchmark analysis, ablation study, hallucination evaluation, production metrics |

## Repository Structure

```text
AI-/
├── README.md
├── papers/
│   ├── README.md
│   ├── template.md
│   └── 2026-iclr-linearrag.md
└── projects/
    └── README.md
```

## Paper Reading System

每篇论文会尽量按照统一结构整理，避免只停留在摘要层面：

1. 这篇论文解决什么问题？
2. 它的核心创新是什么？
3. 方法结构、训练目标、数据和推理流程是什么？
4. 实验结果到底证明了什么？
5. 和已有方法相比，真正的收益在哪里？
6. 方法有哪些假设、代价和局限？
7. 哪些设计可以迁移到真实项目？
8. 如何做一个最小可复现版本？

论文索引放在 [papers/README.md](papers/README.md)，后续每篇论文都会补充独立笔记。

## Engineering Notes

我会把值得复现的论文拆成更小的工程任务，例如：

- 从零实现 Transformer / Attention / KV Cache 等基础模块
- 构建 RAG pipeline，包括文档切分、向量召回、重排、生成和评测
- 复现 LoRA / QLoRA / Distillation 等高效训练方法
- 分析开源模型推理性能、显存占用和部署优化策略
- 对多模态模型做结构拆解和实验记录

项目索引放在 [projects/README.md](projects/README.md)。

## Update Rhythm

这个仓库会作为长期技术输出区持续维护：

- 定期更新近期值得关注的 AI 论文
- 对重要论文补充结构化阅读笔记
- 对可复现方法补充实验代码和工程分析
- 对新模型、新框架、新 benchmark 做简洁跟踪

## Technical Taste

我喜欢的技术内容通常有三个特点：

- Conceptually clear: 能把复杂方法讲清楚，而不是堆术语
- Empirically grounded: 有实验、有指标、有消融，不只讲故事
- Engineering-aware: 能说明真实落地时的数据、算力、延迟、成本和评测问题

AI 发展太快，这个仓库会尽量把碎片化信息沉淀成可检索、可复用、可复现的技术记录。
