---
type: source
tags: [ai, rag, knowledge-graphs, retrieval, developer-tools]
updated: 2026-08-27
source_url: https://graphrag.com/
---

# GraphRAG With a Knowledge Graph

Source: [GraphRAG Pattern Catalog](https://graphrag.com/). Raw capture: [raw/graphrag-com.md](../../raw/graphrag-com.md).

`graphrag.com` is the [[graphrag-pattern-catalog]], a [[neo4j]]-published reference site for [[graphrag]] concepts, graph shapes, retrieval patterns, and research links. The homepage describes the site as a place to learn GraphRAG concepts, prepare data, choose retrieval patterns, and consult a glossary and research appendix.

The key definition is that [[graphrag]] means [[retrieval-augmented-generation]] using a [[knowledge-graphs]] structure. The more useful operational framing is narrower: GraphRAG is a set of [[rag-retrieval-patterns]] where each retrieval pattern depends on a corresponding graph model and preprocessing workflow.

## Key Points

- The catalog treats "GraphRAG" as an overloaded term: it can mean a retrieval method, a pattern family, or an implementation suite such as Microsoft GraphRAG.
- Basic patterns include vector/basic retrieval, pattern matching, Cypher templates, graph-enhanced vector search, metadata filtering, and parent-child retrieval.
- Advanced patterns include dynamic Cypher generation, global community summary retrieval, local retrieval, hypothetical question retrieval, and Text2Cypher.
- Knowledge graph models include domain graphs, lexical graphs, lexical graphs with extracted entities, community summaries, hierarchy, sibling structure, memory graphs, and text sequences.
- The site frames advanced RAG as a pipeline with pre-retrieval, retrieval, post-retrieval, and answer-generation phases.
- Basic vector retrieval is easy to implement but weak when answer context is distributed across many chunks.
- Graph-enhanced vector search adds graph traversal from vector-matched chunks through extracted entities and relationships.
- Global community summary retrieval targets whole-dataset questions by retrieving community summaries built from entity and relationship graphs.
- Local retrieval targets entity-centered exploration by searching entity embeddings and traversing neighboring graph structure.
- Text2Cypher is flexible because the LLM generates the Cypher query from a schema, but it requires guardrails because generated graph queries are not fully reliable.

## Interpretation

The source is useful because it decomposes [[graphrag]] into choices rather than treating it as a single product. That matters for implementation: simple vector retrieval, graph-enhanced vector search, entity-local exploration, whole-dataset community summarization, and Text2Cypher answer different question types and have different preprocessing costs.

The strongest implementation heuristic is to select retrieval patterns by query type and evaluate them. More graph structure can improve recall and context quality, but it brings more moving parts: chunking, embeddings, entity extraction, relationship extraction, entity disambiguation, graph schema design, community detection, summary generation, and query guardrails.

## Follow-ups

- [ ] [GraphRAG reference catalog](https://graphrag.com/reference/) - capture individual retriever patterns and graph-shape entries in more detail.
- [ ] [Microsoft GraphRAG](https://github.com/microsoft/graphrag) - ingest the implementation that popularized the local/global community-summary framing.
- [ ] [Graph Retrieval-Augmented Generation: A Survey](https://doi.org/10.1145/3777378) - capture retrieval paradigms and terminology from the survey linked in the catalog.
- [ ] [neo4j-graphrag](https://neo4j.com/docs/neo4j-graphrag-python/current/) - inspect the practical Neo4j Python package surface.

## Related Pages

- [[graphrag-pattern-catalog]]
- [[graphrag]]
- [[retrieval-augmented-generation]]
- [[knowledge-graphs]]
- [[rag-retrieval-patterns]]
- [[neo4j]]
