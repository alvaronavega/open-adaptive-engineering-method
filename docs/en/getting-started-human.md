# Getting Started for Humans

## Who this is for

This guide is for engineers, leads, and teams introducing OAEM into real software work while preserving human authority.

## What OAEM is (quickly)

OAEM is a methodology for AI-assisted software engineering:
- adaptive by risk and scope;
- evidence-driven;
- model-agnostic;
- harness-agnostic;
- compatible with incremental adoption.

It is not a replacement for engineering judgment.  
It is a framework for making AI-assisted execution more governable and reproducible.

## Human authority baseline

Humans retain authority over consequential decisions, including:
- dependency introduction;
- credentials and external access;
- security posture changes;
- destructive VCS operations;
- release/deploy decisions;
- major architecture tradeoffs.

OAEM helps agents execute bounded work; it does not transfer final accountability.

## Choose adoption depth incrementally

Start with minimum overhead and grow only where risk demands it.

### Option A: Level 0 first
Use OAEM for:
- small local fixes;
- focused validation;
- coherent checkpoints.

Goal: establish evidence and checkpoint discipline without process burden.

### Option B: Level 1 for recurring work
Add:
- explicit acceptance criteria;
- focused regression checks;
- clearer completion statements.

Goal: improve consistency across medium-scoped tasks.

### Option C: Level 2/3 selectively
Use temporary specs or governed change only for higher-risk work.

Goal: invest artifact depth where it reduces real risk.

## Practical rollout sequence

1. Align on OAEM principles (especially evidence over claims and vertical by default).
2. Pick one project stream or team workflow as pilot.
3. Define minimal completion/evidence expectations by depth.
4. Enforce checkpoint discipline for coherent slices.
5. Review friction weekly and classify method/harness/documentation defects.
6. Expand usage only after evidence of value.

## Preserve operational simplicity

Avoid adding heavy artifacts by default.  
OAEM should reduce risk and confusion, not create documentation maintenance debt.

Use links to method docs:
- [Methodology Overview](methodology-overview.md)
- [Adaptive Depth](adaptive-depth.md)
- [Completion Contract](completion-contract.md)
- [Evidence Model](evidence-model.md)

## Anti-patterns to avoid

- forcing high-rigor artifacts for every tiny change;
- accepting completion based on confidence language;
- escalating ordinary bounded defects as human decisions;
- waiting for huge diffs before checkpointing;
- mixing unrelated work into one commit.

## First success signal

Your adoption is working when:
- smaller vertical outcomes complete reliably;
- evidence is current and reproducible;
- checkpoint history helps rollback and diagnosis;
- human escalations are fewer but more meaningful.
