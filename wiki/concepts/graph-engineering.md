---
type: concept
tags: [ai-agents, orchestration, workflows, graphs]
updated: 2026-10-27
---

# Graph Engineering

Graph engineering, in agent workflows, is the design of work units (nodes), handoffs and dependencies (edges), and the conditions that route work through them. A node may be deterministic code, a model call, or a full tool-using agent. [[graph-engineering-explained-in-8min]]

## Research DAG Example

The video shows a research graph with five phases: requirements, topics, information gathering, verification, and synthesis. Independent tasks fan out and later results converge. Because this particular diagram has no backward edge, it is a directed acyclic graph (DAG). The number of workers can be generated for a request rather than fixed in advance. [[graph-engineering-explained-in-8min]]

## Design Tradeoffs

- Parallel workers can lower elapsed time for independent tasks and keep each context focused.
- Handoffs can lose detail or duplicate work; the graph needs clear inputs and outputs for each node.
- More nodes raise token and coordination cost. The video cites Anthropic's workload-specific multi-agent token figures rather than a universal cost ratio.
- A verification stage still needs independent evidence and sound criteria; many agents agreeing is not automatically a strong verifier.
- The pictured DAG is one graph shape. A workflow with retries or feedback is cyclic, and a simple [[loop-engineering|agent loop]] is also a graph.

This is distinct from [[graphrag]] and [[knowledge-graphs]], which use graph structure to represent data and retrieve context. Here the graph controls the work.

## Related Pages

- [[loop-engineering]]
- [[software-factories]]
- [[verifier-bottleneck]]
- [[caleb-writes-code]]
- [[graphrag]]
