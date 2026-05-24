# Paper Reading Notes

This folder tracks AI papers by research direction. Each direction contains three top-tier papers as anchor readings, with additional requested notes kept separately when useful.

## Directory Map

| Direction | Folder | Top-Tier Count | Focus |
| --- | --- | --- | --- |
| Large Language Models | [large-language-models/](large-language-models/) | 3 | Transformer, pretraining, scaling, in-context learning |
| RAG | [rag/](rag/) | 3 | RAG, GraphRAG, retrieval, evidence aggregation |
| AI Agent | [ai-agent/](ai-agent/) | 3 | reasoning-action loops, tool use, memory, self-improvement |
| Multimodal AI | [multimodal-ai/](multimodal-ai/) | 3 | vision-language models, image-text alignment, multimodal reasoning |
| Efficient AI | [efficient-ai/](efficient-ai/) | 3 | LoRA, quantization, efficient fine-tuning and inference |
| Evaluation | [evaluation/](evaluation/) | 3 | benchmarks, truthfulness, holistic model evaluation |
| Agentic RL | [agentic-rl/](agentic-rl/) | 3 | RLHF, preference optimization, multi-agent RL |

## Top-Tier Reading Log

| Direction | Paper | Venue / Year |
| --- | --- | --- |
| Large Language Models | [Attention Is All You Need](large-language-models/2017-neurips-attention-is-all-you-need.md) | NeurIPS 2017 |
| Large Language Models | [BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding](large-language-models/2019-naacl-bert.md) | NAACL 2019 |
| Large Language Models | [Language Models are Few-Shot Learners](large-language-models/2020-neurips-gpt3.md) | NeurIPS 2020 |
| RAG | [REALM: Retrieval-Augmented Language Model Pre-Training](rag/2020-icml-realm.md) | ICML 2020 |
| RAG | [Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks](rag/2020-neurips-rag.md) | NeurIPS 2020 |
| RAG | [LinearRAG: Linear Graph Retrieval Augmented Generation on Large-scale Corpora](rag/2026-iclr-linearrag.md) | ICLR 2026 Poster |
| AI Agent | [ReAct: Synergizing Reasoning and Acting in Language Models](ai-agent/2023-iclr-react.md) | ICLR 2023 |
| AI Agent | [Toolformer: Language Models Can Teach Themselves to Use Tools](ai-agent/2023-neurips-toolformer.md) | NeurIPS 2023 |
| AI Agent | [Reflexion: Language Agents with Verbal Reinforcement Learning](ai-agent/2023-neurips-reflexion.md) | NeurIPS 2023 |
| Multimodal AI | [Learning Transferable Visual Models From Natural Language Supervision](multimodal-ai/2021-icml-clip.md) | ICML 2021 |
| Multimodal AI | [Flamingo: a Visual Language Model for Few-Shot Learning](multimodal-ai/2022-neurips-flamingo.md) | NeurIPS 2022 |
| Multimodal AI | [BLIP-2: Bootstrapping Language-Image Pre-training with Frozen Image Encoders and Large Language Models](multimodal-ai/2023-icml-blip2.md) | ICML 2023 |
| Efficient AI | [LoRA: Low-Rank Adaptation of Large Language Models](efficient-ai/2022-iclr-lora.md) | ICLR 2022 |
| Efficient AI | [GPTQ: Accurate Post-Training Quantization for Generative Pre-trained Transformers](efficient-ai/2023-iclr-gptq.md) | ICLR 2023 |
| Efficient AI | [QLoRA: Efficient Finetuning of Quantized LLMs](efficient-ai/2023-neurips-qlora.md) | NeurIPS 2023 |
| Evaluation | [Measuring Massive Multitask Language Understanding](evaluation/2021-iclr-mmlu.md) | ICLR 2021 |
| Evaluation | [TruthfulQA: Measuring How Models Mimic Human Falsehoods](evaluation/2022-acl-truthfulqa.md) | ACL 2022 |
| Evaluation | [Holistic Evaluation of Language Models](evaluation/2023-tmlr-helm.md) | TMLR 2023 |
| Agentic RL | [Training Language Models to Follow Instructions with Human Feedback](agentic-rl/2022-neurips-rlhf.md) | NeurIPS 2022 |
| Agentic RL | [Direct Preference Optimization: Your Language Model is Secretly a Reward Model](agentic-rl/2023-neurips-dpo.md) | NeurIPS 2023 |
| Agentic RL | [Stronger-MAS: Multi-Agent Reinforcement Learning for Collaborative LLMs](agentic-rl/2026-iclr-stronger-mas.md) | ICLR 2026 |

## Additional Requested Notes

| Direction | Paper | Source |
| --- | --- | --- |
| AI Agent | [ReVeal: Self-Evolving Code Agents via Reliable Self-Verification](ai-agent/2025-reveal.md) | arXiv 2025 / ICLR 2026 submission |
| Agentic RL | [Agent Lightning: Train ANY AI Agents with Reinforcement Learning](agentic-rl/2025-agent-lightning.md) | arXiv 2025 |

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
