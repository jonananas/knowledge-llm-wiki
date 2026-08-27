---
type: concept
tags: [ai, rag, retrieval, knowledge-graphs]
updated: 2026-08-27
---

# RAG Retrieval Patterns

RAG retrieval patterns are reusable strategies for selecting context before answer generation. The [[graphrag-pattern-catalog]] focuses on graph-backed patterns for [[retrieval-augmented-generation]], connecting each retriever to a required [[knowledge-graphs]] shape and preprocessing workflow. [[graphrag-com]]

## Pattern Examples

- Basic/vector retriever: embed the question and retrieve similar chunks.
- Metadata filtering: constrain retrieval using document or chunk metadata.
- Parent-child retriever: retrieve chunks but include broader parent context.
- Graph-enhanced vector search: start with vector-matched chunks, then traverse related entities and relationships.
- Local retriever: search entity embeddings and traverse neighboring graph structure for entity-centered exploration.
- Global community summary retriever: retrieve graph community summaries for whole-dataset questions.
- Text2Cypher: use an LLM to generate a graph query from natural language and a schema.

## Selection Heuristic

Pattern choice should follow query shape:

- Specific fact lookup can often start with basic vector retrieval.
- Questions that need neighboring context may need graph-enhanced vector search or parent-child retrieval.
- Entity exploration needs entity-centered retrieval.
- Corpus-wide themes need global summaries or community retrieval.
- Structured domain questions may fit Cypher templates, dynamic Cypher generation, or Text2Cypher.

The cost increases as patterns require more graph construction, LLM extraction, graph algorithms, generated-query guardrails, and evaluation.

## Related Pages

- [[graphrag]]
- [[retrieval-augmented-generation]]
- [[knowledge-graphs]]
- [[graphrag-pattern-catalog]]
- [[graphrag-com]]
