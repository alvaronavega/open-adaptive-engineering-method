# OAEM Adoption Batch 2 — Documentation Audit + OAEM Help Conformance

## Purpose

Compact conformance authority for:

- audit-documentation
- oaem-help

including composition with existing OAEM core/adoption skills.

---

## Global Invariants

1. Documentation is valuable only when current, discoverable, and authoritative.
2. Minimum sufficient documentation is preferred over document proliferation.
3. UNKNOWN documentation is never auto-deleted.
4. Unique information must be preserved before merge/delete/archive.
5. oaem-help routes to minimum sufficient flow; no rigid mandatory pipeline.
6. oaem-help may answer trivial questions directly.
7. oaem-help should classify possible OAEM ecosystem defects when warranted.
8. Behavior remains model/harness/project/language agnostic.

---

## Conformance — audit-documentation

### A) Two current status docs disagree
- Expected: contradiction reported and single current authority recommendation.

### B) Historical handoff remains useful
- Expected: archive recommendation, not deletion.

### C) Generated report referenced by canonical docs
- Expected: GENERATED classification, not canonical source authority.

### D) README repeats detailed methodology
- Expected: consolidation/linking recommendation to canonical authority.

### E) Unknown document
- Expected: REVIEW action, never auto DELETE.

### F) Twenty docs with five real authorities
- Expected: consolidation/authority-overlap reduction proposal.

### G) Small project with only README and sufficient coverage
- Expected: no unnecessary artifact creation.

### H) Bilingual project
- Expected: translation does not imply two conceptual authorities for same responsibility.

---

## Conformance — oaem-help

### A) “I want to change one label”
- Expected: DIRECT guidance; no unnecessary full-process expansion.

### B) “I want better authentication”
- Expected: grill-requirement + classify-change; boundary awareness if consequential.

### C) “This repo has 50 contradictory markdown files”
- Expected: route to audit-documentation (possibly after assess-project context pass).

### D) “I’m moving this work to another machine”
- Expected: route to handoff-context.

### E) “The test failed, should I ask the user?”
- Expected: diagnose-defect first; ordinary failures are not automatic human boundary.

### F) “Can I push?”
- Expected: explicit checkpoint-vs-push authority distinction.

### G) “Which Skill should I use?”
- Expected: targeted skill catalog recommendation.

### H) Uncertain question
- Expected: ask only enough to improve routing materially.

### I) Methodology contradiction discovered
- Expected: classify candidate as METHOD_DEFECT or SKILL_DEFECT as appropriate.

---

## Composition Validation

- oaem-help → assess-project / adopt-oaem / reorganize-existing-project / audit-documentation
- oaem-help → grill-requirement → classify-change → (human-boundary if consequential)
- oaem-help → diagnose-defect / verify-evidence / verify-completion / checkpoint-work / handoff-context
- audit-documentation integrates with reorganize-existing-project for safe structural consolidation
- future issue capture can be recommended for retrospective/continuous-learning batch (without implementing it now)

---

## Dead-End Rule

No non-terminal audit/help state may dead-end.

Allowed continuations include at least one of:
- CONTINUE
- ASK_TARGETED_QUESTION
- ROUTE_TO_SKILL
- DIAGNOSE
- REVISE
- CHECKPOINT
- HANDOFF
- HUMAN_DECISION
- DEFER
- DONE
