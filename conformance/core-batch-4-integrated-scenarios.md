# OAEM Core Batch 4 — Integrated Execution + Handoff Conformance

## Purpose

Compact conformance authority for integrated OAEM lifecycle behavior using existing core skills plus `handoff-context`.

This authority validates behavior, transitions, and invariants (not provider/harness internals).

---

## Integrated Lifecycle Contract (Reference)

REQUEST  
→ DISCOVER CONTEXT  
→ (if material ambiguity) GRILL REQUIREMENT  
→ CLASSIFY CHANGE  
→ CHOOSE MINIMUM SUFFICIENT DEPTH  
→ SLICE VERTICALLY  
→ IMPLEMENT CURRENT SLICE  
→ VERIFY EVIDENCE

PASS  
→ CHECKPOINT  
→ VERIFY COMPLETION

FAIL  
→ DIAGNOSE DEFECT  
→ IDENTIFY FIRST BROKEN CONTRACT  
→ SMALLEST SOUND FIX  
→ FOCUSED VALIDATION  
→ VERIFY EVIDENCE (loop)

REAL HUMAN BOUNDARY  
→ HUMAN DECISION REQUIRED  
→ CONTINUE / REVISE / DEFER / STOP

VERIFY COMPLETION outcomes  
- MORE WORK → NEXT VERTICAL SLICE  
- COMPLETE → FINAL CHECKPOINT → DONE  
- PARTIAL / interruption → RECOVERY CHECKPOINT (authorized) → HANDOFF CONTEXT → resume later

---

## Core Invariants

1. HANDOFF != COMPLETE
2. Receiver must verify repository/project state before trusting handoff narrative
3. Ordinary bounded defects are autonomous diagnose/fix/verify events (not automatic human escalation)
4. Real consequential authority boundaries require HUMAN_DECISION_REQUIRED
5. Evidence must be sufficient and current for the evaluated state
6. Mandatory failing gate forbids COMPLETE
7. Non-terminal states must continue through: CONTINUE, DIAGNOSE, REVISE, CHECKPOINT, HANDOFF, HUMAN DECISION, DEFER, or DONE
8. Dead-end paths are forbidden

---

## Scenario Set (A–N)

For each scenario:
- **Entry**
- **Expected Flow**
- **Required Assertions**

### A) CLEAR DIRECT FIX

**Entry**: clear low-risk localized correction  
**Expected Flow**: discover → classify DIRECT → single vertical slice → implement → evidence pass → checkpoint → completion complete  
**Required Assertions**:
- no unnecessary grilling
- DIRECT selected with rationale
- focused evidence sufficient
- COMPLETE allowed only after gate/evidence checks

### B) PROGRESSIVE REQUIREMENT DISCOVERY

**Entry**: ambiguous request  
**Expected Flow**: discover → grill loop (question/answer changes next question) → sufficient clarity → classify → continue  
**Required Assertions**:
- question pruning occurs
- no irrelevant interrogation
- stopping condition at sufficient clarity

### C) MULTI-SLICE FEATURE

**Entry**: bounded feature needing multiple outcomes  
**Expected Flow**: slice 1 pass/checkpoint → slice 2 pass/checkpoint → verify completion  
**Required Assertions**:
- slice sequencing by outcomes
- more-work outcome returns to next vertical slice
- checkpoints preserve coherent progress

### D) BOUNDED DEFECT

**Entry**: failed validation for bounded defect  
**Expected Flow**: evidence fail → diagnose → first broken contract → smallest sound fix → focused validation → evidence verify  
**Required Assertions**:
- no unnecessary human escalation
- fix targets responsible layer
- loop closes back to evidence verification

### E) DIAGNOSTIC FAILURE

**Entry**: diagnostic query/tool itself fails  
**Expected Flow**: diagnose diagnostic path → repair diagnostic capability → continue original diagnosis  
**Required Assertions**:
- diagnostic failure is treated as bounded defect
- no false completion
- original defect flow resumes

### F) CONSEQUENTIAL CHANGE

**Entry**: security/product/architecture consequential decision required  
**Expected Flow**: human-boundary → HUMAN_DECISION_REQUIRED  
**Required Assertions**:
- autonomous continuation blocked
- explicit authority boundary recognized

### G) NEW DEPENDENCY

**Entry**: implementation requires adding new dependency  
**Expected Flow**: human-boundary → HUMAN_DECISION_REQUIRED  
**Required Assertions**:
- dependency addition treated as boundary event
- no silent dependency adoption

### H) STALE EVIDENCE

**Entry**: tests pass, then executable state materially changes  
**Expected Flow**: evidence freshness check fails → completion blocked until revalidation  
**Required Assertions**:
- stale evidence cannot prove new state
- revalidation required before COMPLETE

### I) MANDATORY GATE FAILURE

**Entry**: implementation exists but mandatory gate fails  
**Expected Flow**: verify completion fail-closed → diagnose/fix loop  
**Required Assertions**:
- COMPLETE forbidden
- gate failure explicitly represented

### J) DIRTY WORKTREE

**Entry**: unrelated modified files present  
**Expected Flow**: selective checkpoint of scoped changes only  
**Required Assertions**:
- no blind stage-all
- unrelated work preserved
- checkpoint remains coherent/honest

### K) CONTEXT EXHAUSTION

**Entry**: coherent partial work and context near exhaustion  
**Expected Flow**: recovery checkpoint (authorized) → handoff-context with PARTIAL/BLOCKED as applicable  
**Required Assertions**:
- handoff includes exact resume point and next safe action
- no upgrade to COMPLETE

### L) NEW SESSION

**Entry**: new agent/session receives handoff  
**Expected Flow**: verify repo/authorities/evidence freshness → resume safe action  
**Required Assertions**:
- receiver verification performed
- resume grounded in current state, not blind trust

### M) HANDOFF CLAIM CONFLICT

**Entry**: handoff claims PASS, current evidence shows FAIL  
**Expected Flow**: current evidence wins → state corrected → continue from true state  
**Required Assertions**:
- conflict explicitly resolved in favor of authoritative current evidence
- no false COMPLETE

### N) HORIZONTAL EXCEPTION

**Entry**: cross-cutting migration required  
**Expected Flow**: explicit horizontal exception justification + boundary + exit criteria + protected/enabled vertical outcomes  
**Required Assertions**:
- horizontal exception is explicit and bounded
- vertical outcomes remain protected
- exception does not become open-ended layering plan

---

## Composition Validation Matrix

- grill-requirement → classify-change: sufficient clarified intent/risk/constraints
- classify-change → slice-vertically: depth-informed slice rigor
- slice-vertically → verify-evidence: explicit evidence requirements per slice
- verify-evidence → verify-completion: current sufficient evidence + gates + state
- verify-evidence FAIL → diagnose-defect: first broken contract loop
- diagnose-defect → verify-evidence: focused validation and regression evidence
- human-boundary → human decision: consequential authority gating
- checkpoint-work → next slice: coherent continuation without unbounded diff
- partial checkpoint → handoff-context: truthful continuation package
- handoff-context → verified resume: repository/project evidence verification first

---

## Loop Safety Rule

No arbitrary universal retry count is defined in OAEM core.  
Repeated unresolved attempts are evidence that current approach may be wrong.

Required adaptive responses:
- re-diagnose
- reclassify
- re-slice
- change hypothesis
- evaluate human boundary

Harness/project may define concrete circuit-breaker limits externally.

---

## Dead-End Constraint

**DEAD_END_PATHS must equal 0.**

Every non-terminal state must transition to at least one of:
- CONTINUE
- DIAGNOSE
- REVISE
- CHECKPOINT
- HANDOFF
- HUMAN DECISION
- DEFER
- DONE
