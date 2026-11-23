# Getting Started

## Scope

This is the canonical onboarding authority for OAEM Foundation v0.1.

It provides two concise routes:
- **For Humans**
- **For AI Agents**

## For Humans

### 1) Understand OAEM scope
OAEM is a method for governing AI-assisted engineering work with adaptive depth and evidence-oriented completion.

### 2) Classify the change
Assess risk, complexity, uncertainty, and impact.

### 3) Choose minimum sufficient depth
Pick the smallest depth level (0–3) that safely fits the work.

### 4) Adopt incrementally
Do not wait for full-method rollout. Start with bounded slices and increase rigor only when risk requires it.

### 5) Define deterministic evidence
The consumer project defines concrete completion evidence (tests/build/static/security checks as applicable).

### 6) Preserve human authority
Consequential decisions remain human-authorized (dependencies, credentials, external access, security weakening, destructive operations, release/publish/deploy, business/legal decisions).

### 7) Use checkpoints to reduce risk
Prefer:
`vertical slice → focused validation → local checkpoint → continue`

## For AI Agents (foundation bootstrap)

Follow this high-level sequence:

1. discover project authorities;
2. detect OAEM adoption configuration (if present);
3. identify requested outcome;
4. classify risk/complexity/uncertainty;
5. choose minimum sufficient depth;
6. identify available Skills;
7. identify active harness and constraints;
8. identify required deterministic evidence;
9. identify legitimate human boundaries;
10. execute vertically until completion contract is satisfied or a real human boundary occurs;
11. fix bounded defects and continue;
12. checkpoint coherent validated progress;
13. never replace deterministic evidence with model confidence.

## Progressive Requirement Discovery (future skill concept)

OAEM roadmap retains a future `grill-requirement` concept based on progressive requirement discovery:

`question → answer → update understanding → choose next question`

Canonical rule:
**Ask only while an answer can materially change an engineering decision.**

It must not be a fixed questionnaire.

## Related canonical authorities

- [Methodology](methodology.md)
- [Governance](governance.md)
- [Inspirations and Author](inspirations-and-author.md)
