# LinearRAG: Linear Graph Retrieval Augmented Generation on Large-scale Corpora

## Basic Info

- Paper: LinearRAG: Linear Graph Retrieval Augmented Generation on Large-scale Corpora
- Authors: Luyao Zhuang, Shengyuan Chen, Yilin Xiao, Huachi Zhou, Yujing Zhang, Hao Chen, Qinggang Zhang, Xiao Huang
- Institution: Department of Computing, The Hong Kong Polytechnic University
- Venue / Year: ICLR 2026 Poster
- arXiv: https://arxiv.org/abs/2510.10114
- OpenReview: https://openreview.net/forum?id=mCtfkypdm6
- Code: https://github.com/DEEP-PolyU/LinearRAG
- Tags: RAG, GraphRAG, retrieval, multi-hop QA, efficient indexing, Personalized PageRank

## One-Sentence Summary

LinearRAG 用不依赖关系抽取的 Tri-Graph，把 GraphRAG 的图构建简化为实体、句子、段落之间的轻量连接，再通过实体激活和全局重要性聚合完成高效多跳检索。

## Motivation

传统 RAG 对简单事实查询很有效，但在大规模非结构化语料里，相关信息经常分散在多个文档或段落中，单纯向量召回容易漏掉多跳推理链。

GraphRAG 试图用知识图谱组织语料关系，但很多方法依赖 relation extraction 或 triple extraction。问题在于：

- 关系抽取成本高，常常需要额外 LLM 调用或复杂抽取模型。
- 自动抽取的关系容易出错，错误边会把检索引向噪声上下文。
- 局部抽取缺少全局一致性，图结构可能碎片化、重复或冲突。
- 图构建越复杂，索引时间、token 成本和维护成本越高。

LinearRAG 的出发点很清晰：GraphRAG 真正需要的是让相关信息能跨段落连接起来，不一定非要显式抽取关系三元组。

## Core Idea

LinearRAG 放弃显式关系建模，改用 relation-free hierarchical graph，也就是 Tri-Graph。

Tri-Graph 包含三类节点：

- Entity nodes: 由轻量 NER 工具抽取的实体
- Sentence nodes: 由 passage 切分得到的句子
- Passage nodes: 原始语料段落

边只表示包含或提及关系：

- passage contains entity
- sentence mentions entity

这样做的关键好处是：不把自然语言关系压缩成可能错误的三元组，而是保留原文作为知识载体，让 LLM 在生成阶段解释上下文里的关系。

## Method Details

### 1. Token-Free Graph Construction

LinearRAG 的离线构建阶段不调用 LLM。流程是：

1. 将 passage 切分为 sentence。
2. 用 spaCy 等轻量 NER 模型抽取 entity。
3. 构建 passage-entity 和 sentence-entity 两个二部图。
4. 用稀疏矩阵保存邻接关系。

这种设计让新增语料只需要对新 passage 做切句、NER 和边构建，因此复杂度随语料规模线性增长。

### 2. Relevant Entity Activation via Semantic Bridging

在线检索第一阶段是实体激活。

如果只匹配 query 里的实体，容易漏掉多跳问题中间需要的桥接实体。LinearRAG 先计算 query 与 sentence 的语义相关性，再通过 sentence-entity 图传播到相关实体，从而激活那些没有直接出现在 query 里、但对推理链有帮助的中间实体。

为了控制搜索空间，论文还加入 dynamic pruning：只有相关性超过阈值的实体才继续扩展，避免传播过程中引入太多无关实体。

### 3. Passage Retrieval via Global Importance Aggregation

第二阶段把激活实体作为种子，在 passage-entity 图上做全局重要性聚合。论文使用 Personalized PageRank 来计算 passage 的重要性分数，并选取得分最高的 passage 作为最终检索上下文。

这个阶段补上了普通向量检索的短板：它不仅看 query 和 passage 的局部相似度，也利用实体连接关系从全局视角评估哪些 passage 更重要。

## Experiments

### Datasets

论文在四个 benchmark 上评估：

- HotpotQA
- 2WikiMultiHopQA
- MuSiQue
- Medical dataset from GraphRAG-Bench

### Baselines

对比方法包括：

- Zero-shot LLM: LLaMA3-8B, LLaMA3-13B, GPT-3.5-turbo, GPT-4o-mini
- Vanilla RAG: Top-1 / Top-3 / Top-5 retrieval
- GraphRAG baselines: KGP, G-Retriever, RAPTOR, E2GraphRAG, LightRAG, HippoRAG, GFM-RAG, HippoRAG2

### Metrics

- Contain-Match Accuracy
- GPT-Evaluation Accuracy
- Context Relevance
- Evidence Recall

Medical 数据集因为答案是长描述，主要使用 GPT-Evaluation Accuracy。

### Main Results

LinearRAG 在四个数据集上整体超过所有对比方法。论文报告的关键结果包括：

- 在 2WikiMultiHopQA 上达到 70.20% Contain-Acc. 和 63.70% GPT-Acc.
- 在 HotpotQA 上达到 64.30% Contain-Acc. 和 66.50% GPT-Acc.
- 在 MuSiQue 上达到 33.90% Contain-Acc. 和 37.00% GPT-Acc.
- 在 Medical 数据集上达到 63.72% GPT-Acc.

效率方面，论文在 2WikiMultiHopQA 上比较 GraphRAG 方法：

- LinearRAG indexing time: 249.78s
- average retrieval time: 0.093s
- prompt token consumption: 0
- completion token consumption: 0
- average accuracy: 66.95

这说明它的优势不仅是准确率，还包括索引成本和检索成本。

## Strengths

- 避免 relation extraction，把 GraphRAG 里最容易出错、最贵的一步拿掉。
- Tri-Graph 保留原始 passage，减少关系三元组压缩带来的信息损失。
- 线性复杂度和稀疏矩阵实现适合大规模语料扩展。
- 两阶段检索同时利用局部语义桥接和全局重要性传播。
- 对多跳 QA 比 vanilla RAG 更容易召回完整推理链。

## Limitations

- 依赖 NER 质量；如果实体识别失败，图连接会受影响。
- 对实体稀疏、隐喻表达、抽象概念密集的语料，Tri-Graph 的连接可能不够充分。
- Personalized PageRank 和阈值剪枝需要调参，不同领域可能需要重新校准。
- 论文重点是检索和生成准确率，真实生产环境还需要进一步评估增量更新、权限过滤、缓存和在线延迟。

## Engineering Takeaways

这篇论文给 RAG 工程的启发很直接：

- GraphRAG 不一定要先构建显式知识图谱；很多场景只需要稳定的信息连接结构。
- 与其让 LLM 抽取大量关系，不如用轻量 NLP 工具构建便宜、可维护的索引。
- 对多跳检索，实体可以作为跨 passage 的 anchor，sentence 可以作为语义桥接层。
- 稀疏矩阵和 PageRank 类算法仍然很适合做大规模检索系统的底层组件。
- 在工程落地时，要同时看 accuracy、retrieval latency、indexing time 和 token cost。

## Reproduction Plan

### Minimal Goal

实现一个简化版 LinearRAG，在小规模 QA 数据集上验证 relation-free GraphRAG 的检索效果。

### Required Modules

- Passage splitter
- Sentence splitter
- NER extractor, such as spaCy
- Embedding model, such as all-mpnet-base-v2
- Sparse passage-entity and sentence-entity matrices
- Entity activation with semantic bridging
- Passage ranking with Personalized PageRank
- LLM answer generation

### Minimal Experiment

1. 选择 100-500 条 HotpotQA 或 2WikiMultiHopQA 样本。
2. 构建 passage / sentence / entity 三层图。
3. 对每个 query 执行实体激活和 passage ranking。
4. 与 vanilla embedding retrieval top-k 做对比。
5. 记录 evidence recall、answer accuracy、retrieval latency。

## Interview Notes

如果要用一句话解释 LinearRAG：

> LinearRAG 认为 GraphRAG 的核心价值不是抽取复杂关系，而是高效连接分散在语料里的相关证据；它用实体、句子、段落构成 relation-free Tri-Graph，再用语义桥接和 PageRank 做多跳检索。

更技术化的解释：

LinearRAG 把知识图谱构建问题转化成稀疏二部图建模问题。它避免了 relation extraction 的局部错误和全局不一致，通过 NER + semantic linking 构建线性可扩展索引；在线阶段先在 sentence-entity 图上做实体激活，再在 passage-entity 图上用 Personalized PageRank 聚合重要性，因此能在不增加 LLM token 成本的情况下提升多跳 QA 检索质量。
