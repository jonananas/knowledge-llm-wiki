---
type: entity
tags: [ai, rag, knowledge-graphs, retrieval, neo4j]
updated: 2026-08-27
---

# GraphRAG Pattern Catalog

GraphRAG Pattern Catalog is a [[neo4j]]-published reference site at `graphrag.com` for graph-backed [[retrieval-augmented-generation]]. It catalogs [[graphrag]] concepts, graph models, retriever patterns, data preparation tasks, research papers, and glossary terms. [[graphrag-com]]

## Role

The catalog's useful role is pattern selection. Instead of treating GraphRAG as one architecture, it maps question types and retrieval techniques to required graph shapes and preprocessing work. This makes it a design reference for choosing between basic vector search, graph-enhanced vector search, entity-local retrieval, global community summaries, Text2Cypher, and related patterns.

## Pattern Families

- Basic/vector retrieval over embedded chunks.
- Graph-enhanced vector search from matched chunks into connected entities and relationships.
- Parent-child and metadata filtering patterns over lexical graph structure.
- Local retrievers for entity-centered exploration.
- Global community summary retrievers for dataset-level questions.
- Text2Cypher and related query-generation patterns over domain graphs.

## Caveats

The catalog itself notes that the pattern list is not exhaustive and is still evolving. Treat it as a pattern language and source of candidate designs, not as a complete standard or a proof that any single pattern is best for a workload. [[graphrag-com]]

## Related Pages

- [[graphrag-com]]
- [[graphrag]]
- [[rag-retrieval-patterns]]
- [[knowledge-graphs]]
- [[neo4j]]
