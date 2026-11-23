# Problems and Failure Modes

This document captures recurring failure modes that motivated OAEM.

The goal is not to reject specification-driven or skill-driven practices.  
The goal is to address practical governance and execution gaps observed in long-running AI-assisted development.

## 1) Documentation overhead without adaptive depth

### Problem
Structured/specification-driven approaches provide substantial value:
- explicit intent;
- planning clarity;
- traceability;
- quality gates.

But applying the same depth to every task can cause:
- excessive artifacts;
- duplicate information;
- competing sources of truth;
- specification rot and status drift;
- disproportionate context and maintenance cost.

### OAEM response
Use adaptive depth selection based on risk, complexity, uncertainty, scope, and impact.  
Choose the minimum sufficient engineering artifact for the real risk.

---

## 2) Skills alone are not full governance

### Problem
Composable engineering Skills improve execution quality and reuse, but do not always answer:
- which Skill should run when;
- how much rigor is required;
- what evidence is required for completion;
- when an agent may stop;
- when a checkpoint is required;
- when a human decision is genuinely required;
- how cross-harness consistency is maintained.

### OAEM response
Combine composable execution practices with explicit governance artifacts:
- completion contract;
- evidence model;
- checkpoint policy;
- human-boundary policy;
- harness portability contract.

---

## 3) Agents stop one step too early

### Problem
A frequent pattern:
1. the agent analyzes correctly;
2. identifies next executable action;
3. returns “next step: implement …” instead of implementing it.

### OAEM response
Define explicit execution-loop behavior and completion contracts so “analyzing the next step” is not treated as completion.

---

## 4) False completion

### Problem
Observed failure patterns include:
- reporting pass without executing validation;
- reusing stale validation evidence as if current;
- marking partial implementation as complete;
- removing tests while claiming coverage preserved;
- treating model confidence as proof;
- overriding deterministic failures with narrative review.

### OAEM response
Core OAEM rule: **model claims are not execution evidence**.  
Where deterministic verification exists, deterministic evidence is authoritative.

---

## 5) Human boundary confusion

### Problem
Agents often escalate normal engineering defects that should be resolved autonomously (within bounded scope), such as:
- test failures;
- parser bugs;
- documentation drift;
- local tooling defects;
- bounded regressions.

### OAEM response
Distinguish:
- **ordinary bounded defect** → agent fixes and continues;
- **real human boundary** → explicit human decision required.

Examples of real boundaries:
- new dependency introduction;
- credentials/secrets handling;
- external access enablement;
- security policy weakening;
- major architecture replacement;
- destructive version-control operations;
- release/publish/deploy actions;
- business/product decisions.

---

## 6) Cross-machine reproducibility failures

### Problem
Workflows fail when required project state is not committed:
- untracked required files;
- local-only Skills/adapters;
- generated artifacts mistaken as canonical source;
- machine-specific runtime assumptions;
- missing fixtures/scripts;
- machine-specific paths or config.

### OAEM response
Require a **fresh-clone conformance** concept: committed project state should be sufficient for an authorized fresh environment to reconstruct expected workflow behavior.

---

## 7) Multi-agent / multi-harness drift

### Problem
Different harnesses vary in:
- tools and command surfaces;
- permissions and execution semantics;
- output formats;
- limits and hooks.

Without explicit boundaries, one harness can accidentally mutate another harness configuration.

### OAEM response
Use:
- common methodology contract;
- isolated adapter/harness profiles;
- strict rule: one harness must not silently mutate another harness configuration.

---

## 8) Long autonomous runs without checkpoints

### Problem
Long uninterrupted autonomous runs can lead to:
- large unreviewable diffs;
- loss of known-good intermediate states;
- scope drift;
- difficult regression diagnosis.

### OAEM response
Prefer:
- vertical slices;
- focused validation;
- local checkpoint;
- controlled continuation.

Over:
- large monolithic change followed by one final validation.

---

## Summary principle

OAEM does not treat these as isolated prompt failures.  
They are methodology-level failure modes requiring explicit contracts, evidence rules, boundary governance, and iterative learning.
