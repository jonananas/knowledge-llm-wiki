---
type: concept
tags: [knowledge-graphs, graph-databases, ai, data-modeling]
updated: 2026-08-27
---

# Knowledge Graphs

Knowledge graphs represent entities, facts, and relationships as connected graph structures. The [[graphrag-com]] source describes them as flexible models for structured and unstructured data, with nodes for entities or records and typed relationships that can also carry attributes.

## In RAG

In [[graphrag]], a knowledge graph can act as a retrieval memory around the LLM. Instead of only retrieving similar text chunks, the system can traverse document structure, extracted entities, domain relationships, communities, or memory structures to assemble context.

The catalog's common graph elements include:

- Domain nodes and relationships for application-specific facts.
- Document nodes for source documents.
- Chunk nodes for passages with text and embeddings.
- Entity nodes extracted from chunks.
- Community nodes and summaries for higher-level corpus structure.

## Design Tradeoff

Knowledge graphs help when relationships matter: entity context, multi-hop facts, parent-child document structure, dataset-level summaries, or domain-specific query constraints. They are costly when the graph must be extracted from messy text or kept synchronized with fast-changing source data.

## Related Pages

- [[graphrag]]
- [[rag-retrieval-patterns]]
- [[retrieval-augmented-generation]]
- [[neo4j]]
- [[graphrag-com]]
