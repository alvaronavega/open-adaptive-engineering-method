# Adaptive Depth

## Objective

Adaptive depth defines how much process and documentation rigor OAEM requires for a given change.

OAEM rejects both extremes:
- no structure for high-risk work;
- full heavyweight structure for every trivial change.

Core rule: choose the **minimum sufficient artifact** for the real risk.

## Depth selection criteria

Depth should be chosen from practical factors:
- risk of incorrect behavior;
- blast radius if wrong;
- architectural sensitivity;
- security implications;
- uncertainty and unknowns;
- cross-team coordination need;
- reversibility of the change.

## Depth model (v0.1)

### Level 0 — Direct
For local, low-risk, well-understood changes.

Flow:
`intent → implement → focused validation → checkpoint`

Typical examples:
- small local fix with clear cause;
- isolated refactor with no contract change;
- typo/config correction with deterministic verification.

### Level 1 — Ticket
For medium-scoped work requiring explicit acceptance criteria.

Flow:
`goal → acceptance criteria → implementation → focused regression → checkpoint`

Typical examples:
- feature increment in known area;
- moderate behavior extension touching several files;
- bug fix that requires regression coverage and impact check.

### Level 2 — Temporary Spec
For larger but bounded changes with uncertainty.

Flow:
`temporary spec → vertical stories → implementation loop → evidence → completion → retire/archive temporary spec`

Typical examples:
- significant capability addition with staged delivery;
- bounded migration in a subsystem;
- major change that benefits from explicit intermediate decisions.

### Level 3 — Governed Change
For high-risk or consequential changes.

Flow:
`decision artifact → impact analysis → authorized plan → vertical slices → deterministic evidence → human gate`

Typical examples:
- architecture replacement;
- security model change;
- public API/contract changes;
- data-model migrations with recovery concerns.

## Vertical by default at every depth

Depth is not a license for horizontal WIP accumulation.

Default execution at all levels is vertical slicing around independently verifiable outcomes:
- value delivered;
- behavior validated;
- evidence produced;
- risk reduced;
- learning captured.

Horizontal work is allowed only by demonstrated necessity (see [Methodology Overview](methodology-overview.md)).

## Defect handling and depth

Defects are also handled with adaptive depth and vertical slices.

Preferred defect slice:
`observed failure → reproduce → first broken contract → smallest sound correction → regression test → affected regression → evidence → checkpoint`

Avoid broad “while here refactor everything” expansions unless explicitly justified.

## Practical outcomes of adaptive depth

Adaptive depth should reduce:
- documentation overhead;
- context inflation;
- status drift;
- late discovery of regressions.

While preserving:
- traceability where needed;
- evidence integrity;
- decision clarity;
- recoverability through coherent checkpoints.
