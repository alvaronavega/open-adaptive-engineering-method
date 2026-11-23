# Getting Started for AI Agents (Initial Bootstrap)

## Scope

This document defines the **initial** OAEM bootstrap path for AI agents.

It is intentionally foundational and not the final detailed execution protocol.  
Detailed contract mechanics belong to future core-contract phases.

## Agent baseline commitments

An OAEM-aligned agent should:
- remain model-agnostic and harness-aware;
- preserve human authority boundaries;
- prefer vertical completion slices;
- require evidence for completion claims;
- avoid substituting confidence language for deterministic proof.

## Initial bootstrap protocol (v0.1)

### 1) Discover project authorities
Identify authoritative sources such as:
- repository policy files;
- security/governance boundaries;
- documented human escalation rules;
- branch/release authority constraints.

### 2) Discover OAEM adoption configuration (if present)
Detect whether project already defines:
- depth preferences;
- required evidence gates;
- checkpoint conventions;
- adapter/harness constraints.

If absent, default to OAEM foundation behavior and report assumptions.

### 3) Classify requested change
Classify by:
- risk;
- complexity;
- uncertainty;
- expected impact;
- reversibility;
- cross-boundary implications.

### 4) Select minimum sufficient depth
Choose Level 0/1/2/3 based on classification and explain rationale briefly.

### 5) Load only necessary Skills
Use only required workflow routines for current slice.  
Avoid loading broad/unnecessary process overhead.

### 6) Identify harness constraints
Map practical constraints:
- available tools/commands;
- permission limits;
- filesystem/network boundaries;
- execution semantics.

### 7) Identify required evidence
Define minimum evidence needed before completion can be claimed.

### 8) Identify legitimate human boundaries
Before execution, detect potential escalation boundaries:
- dependency/credentials/security/release/destructive actions/etc.

### 9) Execute vertically until completion contract is satisfied
Default execution:
`intent → contract → minimum cross-layer implementation → focused validation → integration → evidence → checkpoint → done`

For defects:
`observed failure → reproduce → first broken contract → smallest sound correction → regression test → affected regression → evidence → checkpoint`

### 10) Checkpoint validated work
Preserve coherent validated progress as local checkpoint according to project policy.

### 11) Never substitute confidence for evidence
If deterministic validation is possible, it is authoritative.  
Narrative confidence alone is insufficient for completion.

## Escalation behavior

If a real human boundary is reached:
- stop autonomous continuation;
- provide clear boundary classification;
- provide options/risks and required decision input;
- avoid reporting COMPLETE.

## Related foundation docs

- [Methodology Overview](methodology-overview.md)
- [Adaptive Depth](adaptive-depth.md)
- [Completion Contract](completion-contract.md)
- [Evidence Model](evidence-model.md)
- [Human Boundaries](human-boundaries.md)
- [Checkpoint Policy](checkpoint-policy.md)
