---
type: concept
tags: [ai, rag, knowledge-graphs, retrieval]
updated: 2026-08-27
---

# GraphRAG

GraphRAG is [[retrieval-augmented-generation]] that uses graph structure during retrieval. In the [[graphrag-com]] source, GraphRAG is defined less as one algorithm and more as a family of [[rag-retrieval-patterns]] where each pattern depends on a particular [[knowledge-graphs]] model.

## Why Graph Structure Helps

Plain vector retrieval usually starts from chunks whose embeddings resemble the query. GraphRAG can add explicit relationships:

- Documents and chunks can be linked through lexical structure.
- Chunks can be connected to extracted entities and relationships.
- Domain entities can be connected through business or scientific facts.
- Communities can summarize higher-level structure across a corpus.
- Memory graphs can represent episodic, semantic, procedural, or temporal agent memory.

These relationships can retrieve context that would be missed by text similarity alone.

## Cost Surface

GraphRAG adds preprocessing and operational costs. Depending on the pattern, a system may need chunking, embeddings, entity extraction, relationship extraction, disambiguation, schema design, graph algorithms, community summarization, query templates, or guardrails for generated graph queries.

The practical question is not "Should this be GraphRAG?" but which graph structure, if any, improves retrieval for the query types the system must answer.

## Related Pages

- [[graphrag-com]]
- [[graphrag-pattern-catalog]]
- [[retrieval-augmented-generation]]
- [[knowledge-graphs]]
- [[rag-retrieval-patterns]]
