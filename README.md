# AI Algorithm Engineer Portfolio

This repository records my ongoing learning and implementation practice in modern AI algorithms. It is organized around paper reading, reproduction notes, engineering takeaways, and small experiments that can become interview-ready projects.

I use this repo as a public learning log: read papers, extract core ideas, reproduce key components where possible, and connect research methods to practical model-building problems.

## Focus Areas

- Large language models: Transformer architecture, instruction tuning, alignment, long-context modeling, tool use, and agent workflows
- Retrieval-augmented generation: embedding models, vector search, reranking, chunking, evaluation, and production RAG design
- Multimodal learning: vision-language models, contrastive learning, image-text alignment, and multimodal reasoning
- Efficient training and inference: LoRA, QLoRA, distillation, quantization, pruning, batching, KV cache, and serving optimization
- Computer vision foundations: CNNs, ViT, detection, segmentation, diffusion models, and generative vision systems
- Model evaluation: offline metrics, ablation design, error analysis, benchmark reading, and practical evaluation reports

## Repository Structure

```text
AI-/
├── README.md
├── papers/
│   ├── README.md
│   └── template.md
└── projects/
    └── README.md
```

## Current Learning System

My paper-reading workflow is designed to connect research papers with implementation ability:

1. Identify the problem setting and why it matters.
2. Summarize the core method in plain language.
3. Trace the model architecture, loss design, data pipeline, and training strategy.
4. Compare with related work and understand the real improvement.
5. Extract reusable engineering ideas.
6. Convert the paper into a small reproduction, experiment, or interview explanation.

## Paper Reading Log

The detailed reading list lives in [papers/README.md](papers/README.md). Each paper note follows a consistent structure:

- Motivation
- Method summary
- Architecture and training details
- Key equations or algorithms
- Experiments and ablations
- Strengths and limitations
- Engineering takeaways
- Possible reproduction plan

## Project Roadmap

The project index lives in [projects/README.md](projects/README.md). Planned project directions:

- Build a minimal Transformer from scratch
- Implement a small RAG pipeline with embedding, retrieval, reranking, and evaluation
- Reproduce LoRA fine-tuning on a lightweight open-source model
- Implement common CV modules such as ViT blocks and attention visualization
- Create concise experiment reports from paper reproduction attempts

## What I Am Building Toward


- Research understanding: quickly reading papers and extracting the key algorithmic contribution
- Engineering implementation: translating papers into clean, testable, reproducible code
- Practical judgment: knowing when a method is useful, what its assumptions are, and how to evaluate it

This repository will be updated continuously as I read new papers and complete experiments.
