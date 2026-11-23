# Origin and Motivation

## Why OAEM exists

OAEM emerged from practical, repeated friction in long-running AI-assisted software engineering work.

The initial motivation was not to invent another prompt pack or another agent wrapper.  
It was to close recurring gaps between:
- structured engineering intent;
- actual execution behavior from agents;
- trustworthy completion evidence;
- reproducibility across machines and harnesses;
- sustainable workflow overhead.

## Founding problem statement

Teams and individual engineers can get strong outcomes from specification-driven and skill-driven approaches.  
However, over time, recurring failure patterns appear when methodology governance is incomplete.

OAEM addresses this by defining a methodology contract that is:
- adaptive by risk and complexity;
- evidence-driven;
- model-agnostic;
- harness-agnostic;
- explicit about human decision boundaries;
- iterative and learnable from real use.

## Practical friction categories

OAEM was shaped by concrete patterns observed in real engineering work:

1. Documentation depth was often static when risk was dynamic.
2. Skills improved execution quality but did not fully define governance.
3. Agents frequently stopped one action too early.
4. Completion claims were accepted without current deterministic evidence.
5. Human-boundary decisions were inconsistently applied.
6. Workflows failed to reproduce in fresh environments.
7. Multi-agent and multi-harness setups drifted over time.
8. Long autonomous runs lacked reviewable checkpoints.

These are documented in detail in:
- [Problems and Failure Modes](problems-and-failure-modes.md)

## Design intent for v0.1

OAEM v0.1 establishes a foundation, not a final standard.

It prioritizes:
- identity and scope clarity;
- documented failure modes;
- adaptive depth baseline;
- governance principles;
- language and translation policy;
- future-ready structure for contracts, adapters, conformance, and method evolution.

## Non-goals at foundation stage

OAEM v0.1 does not attempt to:
- ship full implementation adapters for all harnesses;
- lock users into a specific model, IDE, language, or CI stack;
- replace project-specific engineering standards;
- claim proven industry-wide performance.

## Method evolution philosophy

OAEM is intended to evolve through a loop:
1. use method in real work;
2. capture friction with reproducible context;
3. classify method vs harness vs implementation defect;
4. improve methodology assets;
5. add conformance/regression coverage;
6. release refined versions.

This is how OAEM intends to remain practical instead of theoretical.
