# GraphRAG with a Knowledge Graph

Source URL: https://graphrag.com/
Fetch date: 2026-08-27

Publisher: Neo4j, Inc.
License noted by source: CC BY 4.0
Site last updated: 2025-07-11

Related pages inspected:
- Intro to GraphRAG: https://graphrag.com/concepts/intro-to-graphrag/
- Intro to Knowledge Graphs: https://graphrag.com/concepts/intro-to-knowledge-graphs/
- Text Chunking: https://graphrag.com/guides/chunking/
- GraphRAG Pattern Catalog: https://graphrag.com/reference/
- Basic Retriever: https://graphrag.com/reference/graphrag/basic-retriever/
- Graph-Enhanced Vector Search: https://graphrag.com/reference/graphrag/graph-enhanced-vector-search/
- Global Community Summary Retriever: https://graphrag.com/reference/graphrag/global-community-summary-retriever/
- Local Retriever: https://graphrag.com/reference/graphrag/local-retriever/
- Text2Cypher: https://graphrag.com/reference/graphrag/text2cypher/
- Research appendix: https://graphrag.com/appendices/research/
- Glossary: https://graphrag.com/appendices/glossary/

## Summary

`graphrag.com` is the GraphRAG Pattern Catalog, a Neo4j-published reference site for Retrieval Augmented Generation patterns that use knowledge graphs. The site defines GraphRAG as RAG using a knowledge graph, but immediately narrows the practical meaning: it is a set of retrieval patterns that leverage graph structure, where each pattern needs a specific graph shape and preprocessing approach.

The catalog is organized around concepts, how-to guides, reference patterns, knowledge graph models, research links, and a glossary. Its most useful contribution is not a single implementation. It is a pattern language for deciding how graph structure should be used during retrieval.

## Main points

- GraphRAG is presented as RAG using knowledge graphs, not as one fixed algorithm.
- The site explicitly notes ambiguity in the term: GraphRAG can refer to a retrieval method, a set of patterns, or a full software suite such as Microsoft's GraphRAG.
- The catalog focuses on retrieval patterns and their required graph patterns.
- Basic retriever patterns include basic/vector retrieval, pattern matching, Cypher templates, graph-enhanced vector search, metadata filtering, and parent-child retrieval.
- Advanced patterns include dynamic Cypher generation, global community summary retrieval, local retrieval, hypothetical question retrieval, and Text2Cypher.
- Knowledge graph models include domain graphs, lexical graphs, parent-child lexical graphs, lexical graphs with extracted entities, lexical graphs with community summaries, hierarchical or sibling structure, memory graphs, and text sequences.
- The site distinguishes advanced RAG phases: pre-retrieval, retrieval, post-retrieval, and answer generation.
- Basic vector retrieval is easy to implement but weak when relevant context is spread across many chunks.
- Graph-enhanced vector search starts from vector-similar chunks, then traverses entity and relationship structure to retrieve richer context.
- Global community summary retrieval targets dataset-level or "global" questions by retrieving summaries of graph communities.
- Local retrieval starts from similar entities and traverses connected entities and relationships for entity-centered exploration.
- Text2Cypher translates natural language plus a graph schema into Cypher, which is flexible but less reliable and needs guardrails such as syntax checks, read-only execution, retries, or human review.
- Knowledge graphs are described as flexible memory companions for LLMs, representing entities and facts as nodes connected by typed relationships.
- Chunk nodes are central to many patterns and usually have text plus an embedding.
- Chunking strategies listed include fixed splitting, hierarchical document chunking, sentence chunking, and semantic chunking.
- The research appendix lists survey and implementation papers, including Microsoft GraphRAG, LightRAG, HippoRAG, HybridRAG, GraphReader, PathRAG, and related graph-reasoning work.

## Interpretation

The catalog's practical value is that it separates graph-backed RAG into reusable retrieval patterns. That avoids treating "GraphRAG" as a monolith. A system might only need metadata filtering or parent-child retrieval; another might justify extracted entities, community detection, and summary graphs.

The repeated tradeoff is retrieval power versus preprocessing and operational cost. Adding graph structure can recover context that plain vector search misses, but entity extraction, relationship extraction, disambiguation, community detection, summary generation, and schema management all add cost and failure modes.

The catalog also makes evaluation central by implication: it says choosing the right pattern requires experimentation with retrieval patterns and evaluating results. One pattern is unlikely to serve every query type.

## Links

- Home: https://graphrag.com/
- Reference catalog: https://graphrag.com/reference/
- GitHub organization: https://github.com/graphrag/
- Neo4j: https://neo4j.com/
