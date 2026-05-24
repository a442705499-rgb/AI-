# Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks

## Basic Info

- Paper: Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks
- Authors: Patrick Lewis et al.
- Venue / Year: NeurIPS 2020
- Link: https://arxiv.org/abs/2005.11401
- Tags: RAG, dense retrieval, generation, knowledge-intensive NLP

## One-Sentence Summary

RAG combines a dense retriever with a sequence-to-sequence generator so the model can condition generation on retrieved external documents.

## Core Idea

The model retrieves relevant passages from a large corpus and feeds them into a generator such as BART. This separates parametric memory from non-parametric memory: the model keeps language generation ability in its parameters while retrieving factual knowledge from an external index.

## Why It Matters

- Establishes the modern retrieval-augmented generation pattern.
- Reduces reliance on model parameters as the only knowledge store.
- Makes knowledge updates possible by changing the retrieval corpus.

## Engineering Takeaways

- Retrieval quality is often the bottleneck of generation quality.
- External knowledge makes systems more updateable and inspectable.
- RAG evaluation must consider both evidence retrieval and final answer quality.

## Reproduction Plan

Build a small RAG pipeline with a dense retriever, a vector index, top-k passage retrieval, and a generator. Compare answer quality with and without retrieved context.
