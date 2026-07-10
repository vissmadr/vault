---
context:
  - "[[Large Language Model (LLM)]]"
---

#empty
#wip

# OpenAI Models

ad

---

Overall comparison:

```
Model              Relative API price    Best use                                                       My assessment
━━━━━━━━━━━━━━━━━  ━━━━━━━━━━━━━━━━━━━━  ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
5.6 Sol                          100%    Difficult agentic coding, architecture, ambiguous debugging    Best quality; escalation model
─────────────────  ────────────────────  ─────────────────────────────────────────────────────────────  ──────────────────────────────────────────────────────
5.5                              100%    Complex coding and general professional work                   Stable fallback; less compelling if Sol is available
─────────────────  ────────────────────  ─────────────────────────────────────────────────────────────  ──────────────────────────────────────────────────────
5.6 Terra                         50%    Everyday serious coding and knowledge work                     Best default
─────────────────  ────────────────────  ─────────────────────────────────────────────────────────────  ──────────────────────────────────────────────────────
5.4                               50%    Established lower-cost frontier option                         Mostly superseded by Terra when Terra is available
─────────────────  ────────────────────  ─────────────────────────────────────────────────────────────  ──────────────────────────────────────────────────────
5.6 Luna                          20%    Fast, inexpensive, bounded agentic tasks                       Useful economy tier
─────────────────  ────────────────────  ─────────────────────────────────────────────────────────────  ──────────────────────────────────────────────────────
5.4 mini                          15%    Simple, high-volume, well-specified work                       Cheapest dependable automation tier
─────────────────  ────────────────────  ─────────────────────────────────────────────────────────────  ──────────────────────────────────────────────────────
5.3 Codex Spark         Not finalized    Real-time collaborative editing                                Choose for latency, not autonomy
```

Recommendation:

```
 Work                                              Model
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
 Normal feature implementation                     Terra high
────────────────────────────────────────────────  ─────────────────────────────────
 Local bug with a clear reproduction               Terra high
────────────────────────────────────────────────  ─────────────────────────────────
 Documentation or task-spec updates                Terra medium
────────────────────────────────────────────────  ─────────────────────────────────
 Mechanical rename or narrow config edit           Luna medium
────────────────────────────────────────────────  ─────────────────────────────────
 File discovery, summaries, repetitive cleanup     Luna or 5.4 mini
────────────────────────────────────────────────  ─────────────────────────────────
 Architecture or dependency-boundary change        Sol high
────────────────────────────────────────────────  ─────────────────────────────────
 Difficult renderer/lifetime/state bug             Sol high, then max if necessary
────────────────────────────────────────────────  ─────────────────────────────────
 Broad refactor spanning engine/gameplay/apps      Sol high
────────────────────────────────────────────────  ─────────────────────────────────
 Final review of a risky Terra implementation      Sol high
────────────────────────────────────────────────  ─────────────────────────────────
 Rapid edit while you actively steer every step    Spark
```
