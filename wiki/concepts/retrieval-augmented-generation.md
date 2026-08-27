---
type: concept
tags: [ai, rag, retrieval, llms]
updated: 2026-08-27
---

# Retrieval-Augmented Generation

Retrieval-augmented generation, or RAG, is a pattern for grounding an LLM response in retrieved external context. A user query is used to find relevant source material, that material is added to the prompt or orchestration context, and the LLM generates an answer from both the user request and retrieved evidence.

The [[graphrag-com]] source defines GraphRAG as RAG using a [[knowledge-graphs]] structure. That makes [[graphrag]] a retrieval-side specialization of RAG rather than a replacement for the full generation workflow.

## Pipeline Shape

The GraphRAG Pattern Catalog frames advanced RAG as four phases:

- Pre-retrieval: query rewriting, entity extraction, query expansion, and similar preparation.
- Retrieval: finding relevant context.
- Post-retrieval: reranking, pruning, and context shaping.
- Answer generation: giving the selected context to the LLM.

## Design Concern

RAG quality depends heavily on the retrieval step. Basic vector search is simple and often effective, but can miss context when relevant information is distributed across chunks, linked through entities, or requires global summaries. [[rag-retrieval-patterns]] and [[graphrag]] exist to widen the retrieval design space.

## Related Pages

- [[graphrag]]
- [[rag-retrieval-patterns]]
- [[knowledge-graphs]]
- [[graphrag-com]]
