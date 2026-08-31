# Expert index

Select the minimal panel the task requires. The coordinator understands the
request in detail and decides who sits at the roundtable. Select an expert
only when the scope contains evidence for that lens, and let one expert cover
several concerns before adding another.

Always seat the [Tech lead](tech-lead.md) in every roundtable. It is the
standing current-context role: it uses query-driven web research and returns
`tech-lead-current-brief.json` instead of asking the Librarian for books.

For a localized, low-risk architecture review with one main concern, start one
fresh book-guided expert agent plus the standing Tech lead and do not start a
wider panel. That primary lens may use the programming-language expert
definition. A language, schema, or configuration format appearing in the
change is not enough evidence for its own seat; language semantics must
materially affect the risk and remain uncovered by the primary expert.

- [Design principles](design-principles-architect.md): clarity, boundaries,
  responsibilities, contracts, dependency direction, maintainability.
- [Pragmatic engineering](pragmatic-architect.md): coupling, feedback, reversibility,
  accidental complexity.
- [Systems](systems-architect.md): data flow, resources, failure, compatibility,
  operations.
- [Data](data-architect.md): schemas, storage, consistency, pipelines,
  retention, privacy.
- [Reliability](reliability-expert.md): SLOs, alerting, capacity, resilience,
  on-call and human factors.
- [Testing](testing-expert.md): test strategy, behavior coverage, determinism,
  eval and regression gates.
- [Algorithmic](algorithmic-expert.md): algorithms, performance, numerical work.
- [Change Management](change-management-expert.md): refactors, migrations,
  rollout, rollback.
- [Security](security-expert.md): adversaries, trust boundaries, abuse,
  defensive controls.
- [Cloud](cloud-architect.md): distributed, hosted, networked, or infrastructure
  systems.
- [AI](ai-architect.md): foundation models, RAG, generative AI, and agents.
- [ML](ml-architect.md): datasets, training, predictive models, drift, and
  experimentation.
- [Programming language](programming-language-expert.md): idioms and engineering
  practice for one materially involved language or DSL and its closely coupled
  ecosystem.

Every selected book-guided expert follows the
[shared expert protocol](expert-protocol.md). Spawn one isolated shared
[Librarian](librarian.md) for every workflow; it is a support role, not another
review lens. The Tech lead is the only non-book expert and never contacts the
Librarian. The shared [workflow](../workflow.md) defines coordinator handoffs,
validation, and verification; the architecture review skill defines its fast
path.

Selection hints:

- Planning usually needs Systems or Pragmatic plus Change Management. Add a
  domain specialist only when the planned system uses that domain.
- Architecture review usually needs Systems plus the lens closest to the stated
  concern.
- A small-change architecture review starts one primary expert unless its
  evidence reveals a cross-cutting or high-risk concern. The Tech lead still
  runs because it is a standing source-check role, not a reason to widen the
  expert panel.

Treat every agent as a small service. Each receives only the
contracts named by its interface, and only the coordinator writes user-facing
prose in the invoking skill's output format.

Attribute every finding and every upheld practice in the final report to the
lens that produced it, and hold both to the same evidence bar. Move an expert
whose analysis produced nothing the report uses out of the seated panel and
into the report's dropped-at-synthesis list, with the reason.
