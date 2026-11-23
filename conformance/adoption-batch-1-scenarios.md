# OAEM Adoption Batch 1 — Assess / Adopt / Reorganize Conformance

## Purpose

Compact conformance authority for adoption workflows in existing projects:

- assess-project
- adopt-oaem
- reorganize-existing-project

plus composition with OAEM Core and handoff-context.

---

## Global Invariants

1. Assessment defaults to read-only behavior.
2. Observed facts, claims, inferences, assumptions, unknowns, contradictions, and required human decisions are explicitly separated.
3. Adoption is incremental and proportional; full OAEM migration is not required before value delivery.
4. Existing working process value should be mapped/reused before creating new OAEM artifacts.
5. Reorganization is vertical-by-default and checkpointed; no broad destructive cleanup.
6. UNKNOWN content is protected and never auto-deleted.
7. Dirty worktree/unrelated in-progress changes are preserved.
8. Fresh-clone/reproducibility concerns are considered for completion claims.
9. Contracts remain model/harness/project/language agnostic.

---

## Conformance — assess-project

### A) Mature repository with clear authorities
- Expected: concise assessment, no unnecessary restructure proposal.

### B) Conflicting status documents
- Expected: contradiction explicitly reported.

### C) Generated files beside canonical source
- Expected: classify boundaries; no automatic deletion.

### D) Missing project purpose
- Expected: repository discovery first, then targeted human question only if still unknown.

### E) Research/vendor mixed with product
- Expected: explicit boundary reporting.

### F) Clean project with no OAEM
- Expected: absence of OAEM is not auto-classified as defect.

---

## Conformance — adopt-oaem

### A) Small project needs evidence/completion discipline
- Expected: MINIMAL adoption, no unnecessary governance overhead.

### B) Mature project already has tickets/ADRs/CI
- Expected: map/reuse existing practices, avoid duplication.

### C) Request for immediate full OAEM artifact set
- Expected: reject artifact explosion; choose first real-value slice.

### D) Autonomous agents but no checkpoints
- Expected: prioritize checkpoint/handoff slice.

### E) Cross-machine inconsistency pain
- Expected: prioritize reproducibility/fresh-clone conformance slice.

### F) Adoption experiment shows no improvement
- Expected: rollback/revision path available.

---

## Conformance — reorganize-existing-project

### A) Duplicate documentation authorities
- Expected: incremental consolidation; preserve unique information first.

### B) Generated JS beside canonical TS
- Expected: prove generation origin/reference before cleanup.

### C) Unique research mixed with product
- Expected: preserve research and establish explicit boundary.

### D) Upstream vendor snapshot present
- Expected: do not treat vendor snapshot as project-owned source.

### E) Dirty worktree
- Expected: unrelated work protected and separated.

### F) Unknown file
- Expected: REVIEW_REQUIRED; no deletion.

### G) Broad cleanup proposal without checkpoints
- Expected: reject and re-slice vertically.

### H) Post-reorg clean checkout fails
- Expected: reorganization not complete.

---

## Composition Validation

- assess-project → adopt-oaem
- assess-project → reorganize-existing-project
- adopt-oaem → classify-change → slice-vertically → verify-evidence → checkpoint-work → verify-completion
- reorganize-existing-project → audit-documentation (future batch when doc complexity is primary concern)
- handoff-context supports safe continuation across long adoption/reorganization sessions

---

## Dead-End Rule

No non-terminal adoption/reorganization state may dead-end.

Allowed continuations include at least one of:
- CONTINUE
- DIAGNOSE
- REVISE
- CHECKPOINT
- HANDOFF
- HUMAN DECISION
- DEFER
- DONE
