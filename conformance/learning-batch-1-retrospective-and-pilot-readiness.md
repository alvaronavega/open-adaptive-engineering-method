# OAEM Learning Batch 1 — Retrospective + Defect Learning + Pilot Readiness

## Purpose

Compact authority for:

- retrospective learning behavior
- defect classification discipline
- pilot-readiness verification (without adding new OAEM features)

---

## Core Learning Invariants

1. Retrospective is not a status report.
2. Findings must be evidence-grounded and root-cause status must remain honest.
3. Product defects must not be confused with method/skill/adapter/harness defects.
4. UNKNOWN is valid when evidence is insufficient.
5. Not every incident justifies immediate methodology change.
6. Positive learning must be captured, not only failures.
7. oaem-help routes relevant method/skill/harness/adapter confusion to retrospective.
8. Handoff may preserve incomplete retrospective state without claiming closure.
9. Skill catalog growth is frozen unless reusable missing responsibility is evidenced.

---

## Conformance Scenarios (A–L)

### A) PRODUCT BUG
- Condition: implementation incorrect, OAEM behavior correct.
- Expected: PRODUCT_DEFECT primary classification.

### B) FALSE COMPLETION
- Condition: COMPLETE reported while mandatory gate fails.
- Expected: classify as METHOD_DEFECT / SKILL_DEFECT / HARNESS_DEFECT according to first broken contract + add conformance/regression evidence.

### C) FALSE HUMAN BOUNDARY
- Condition: normal test failure escalated as human boundary.
- Expected: HARNESS_DEFECT or SKILL_DEFECT classification; route back to diagnose/fix/verify loop.

### D) DOCUMENT EXPLOSION
- Condition: small change produces many redundant docs.
- Expected: DOCUMENTATION_DEFECT (and possibly METHOD/SKILL contributor); consolidate authority, no new document proliferation.

### E) CROSS-MACHINE FAILURE
- Condition: required skill exists only locally.
- Expected: ADOPTION_CONFIGURATION_DEFECT or reproducibility/configuration defect classification.

### F) SKILL ROUTING ISSUE
- Condition: oaem-help recommends high rigor for trivial label update.
- Expected: SKILL_DEFECT classification for routing contract behavior.

### G) ADAPTER CONTEXT LOSS
- Condition: adapter loses project authority between sessions.
- Expected: ADAPTER_DEFECT classification.

### H) SUCCESSFUL VERTICAL SLICE
- Condition: coherent small slice validates and checkpoints cleanly.
- Expected: positive learning captured; action NO_CHANGE or CLARIFY guidance.

### I) UNCERTAIN CAUSE
- Condition: symptoms cannot separate skill vs harness cause.
- Expected: UNKNOWN + bounded experiment; no premature method change.

### J) RECURRING PROBLEM
- Condition: same evidenced defect repeats across projects/harnesses.
- Expected: methodology-level review justified (potential METHOD_DEFECT path).

### K) CONTEXT EXHAUSTION
- Condition: partial work preserved via checkpoint + handoff.
- Expected: successful recovery learning captured.

### L) CONTRIBUTOR CRITICISM
- Condition: well-supported counterexample challenges OAEM guidance.
- Expected: evaluate evidence; do not dismiss due to status-quo bias.

---

## Retrospective Evidence Contract (Required Fields)

Each finding should preserve:

- OBSERVED_BEHAVIOR
- REPRODUCTION
- EXPECTED_BEHAVIOR
- ACTUAL_BEHAVIOR
- EVIDENCE
- IMPACT
- ROOT_CAUSE_STATUS: PROVEN | HYPOTHESIS | UNKNOWN
- PRIMARY_CLASSIFICATION
- ACTION_DECISION

---

## Action Decision Set

Allowed decisions:

- NO_CHANGE
- CLARIFY_EXISTING_AUTHORITY
- UPDATE_SKILL
- UPDATE_METHOD
- UPDATE_ADAPTER
- UPDATE_HARNESS
- ADD_CONFORMANCE_SCENARIO
- ADD_REGRESSION_TEST
- CHANGE_ADOPTION_CONFIGURATION
- RUN_EXPERIMENT
- HUMAN_REVIEW_REQUIRED
- DEFER

---

## Change Threshold

Immediate change is justified when reproducible + material + low-risk/high-clarity correction, or when core safety/completion invariants are violated.

Otherwise:

record → recurrence tracking → bounded experiment → evidence → deliberate change.

---

## OAEM Help / Handoff Integration

- oaem-help routes method/skill/harness/adapter complaints to retrospective
- handoff-context preserves unresolved retrospective state with evidence locations and exact next learning action
- unresolved classification must not be reported as complete learning

---

## Pilot Readiness Checklist (Minimum)

Required catalog for first real-project pilot:

1. grill-requirement
2. classify-change
3. slice-vertically
4. verify-evidence
5. verify-completion
6. diagnose-defect
7. human-boundary
8. checkpoint-work
9. handoff-context
10. assess-project
11. adopt-oaem
12. reorganize-existing-project
13. audit-documentation
14. oaem-help
15. retrospective

For each skill verify:

- exists
- trigger clarity
- non-trigger clarity
- outcome clarity
- human-boundary clarity where applicable
- composition path exists
- no model/harness/project lock-in

---

## Pilot Protocol (Define, Do Not Execute Here)

Future pilot should observe at least:

- skill selection correctness
- progressive questioning quality
- minimum sufficient rigor behavior
- vertical slicing quality
- bounded-defect continuation quality
- false human-boundary rate
- false completion rate
- checkpoint quality
- handoff quality
- cross-session recovery
- documentation overhead
- fresh-clone assumptions
- model/harness portability
- human intervention split:
  - NECESSARY_HUMAN_INTERVENTION
  - FALSE_HUMAN_INTERVENTION
- method/skill/adapter/harness defect incidence

Pilot safety prerequisites:

- known safe checkpoint
- auto-push disabled
- destructive git disabled
- credentials/external access separated
- local commit authorization aligns with project policy
- mandatory validations identified
- rollback path defined
- research/vendor/upstream boundaries identified where relevant
