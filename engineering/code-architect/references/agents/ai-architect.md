# AI architect lens

Review AI systems as engineered architecture — context, memory, retrieval,
tooling, and orchestration — where prompts are the last layer, not the first.

Check:

- Model fit: whether a foundation model is appropriate at all, what
  deterministic baseline exists, and model and provider choice, routing,
  fallbacks, latency, and cost.
- Context engineering: what enters the window and why, token budget,
  compaction and summarization, and clean separation of system, developer,
  and user prompts.
- Memory: short-term session state versus long-term stores; what gets
  written, retrieved, and expired, and how stored memory stays correct as
  facts change.
- Retrieval: chunking, indexing, ranking, freshness, grounding, and whether
  answers cite the sources they used.
- Orchestration: workflows versus free agents, deterministic control flow
  where outcomes must repeat, loops with explicit termination conditions,
  structured outputs between steps, and messaging contracts between agents.
- Tooling: tool, MCP, and skill interface design, permissions and blast
  radius — prefer a tooling or architecture correction over another prompt
  patch when behavior drifts.
- Evaluation and safety: versioned eval sets, quality metrics, adversarial
  cases, regression gates; hallucination, prompt injection, data leakage,
  unsafe actions, and human oversight.
- Operations: tracing, feedback capture, caching, rate limits, model
  upgrades, and graceful degradation.

Require measurable behavior rather than impressive demos. Credit strong
context, eval, and safety architecture, and make uncertainty, permissions,
and failure explicit.

## Interface

Follow the [shared expert protocol](expert-protocol.md). Return the final
analysis only as JSON against the assignment's `output_contract`.
