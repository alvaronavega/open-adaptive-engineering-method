---
name: adopt-oaem
description: Incrementally adopt OAEM in existing projects by mapping current practices first, selecting minimum needed OAEM capabilities, and avoiding artifact/process explosion.
---

# Adopt OAEM Skill

## Purpose

Introduce OAEM incrementally into an existing project without requiring full migration before useful delivery.

## Canonical Rule

DO NOT REQUIRE COMPLETE OAEM ADOPTION BEFORE DELIVERING VALUE.

Adoption depth must be proportional to:

- project maturity
- current pain
- risk
- team/human capacity
- existing process
- tooling constraints
- AI/harness environment

## Adoption Modes (Practical, Non-Certification)

### MINIMAL

Focus on:

- classify work by real risk;
- vertical slicing;
- evidence over claims;
- completion checks.

### CHECKPOINTED

Add:

- local checkpoints;
- handoff-context for continuity;
- bounded autonomous execution discipline.

### GOVERNED

Add:

- stronger decision records;
- explicit human-boundary policy;
- stronger evidence expectations;
- fresh-clone conformance attention.

### FULL / ADVANCED

Add when justified:

- broader skill catalog coverage;
- harness adapter strategy;
- conformance suite expansion;
- learning/feedback loops.

Do not imply every project should reach maximum mode.

## Preserve Existing Value

Map existing practices to OAEM before adding new artifacts/process.

Reuse when possible, for example:

- existing tickets may satisfy ticket depth;
- existing ADRs may satisfy governed decisions;
- existing CI gates may provide deterministic evidence;
- existing contribution rules may satisfy checkpoint discipline;
- existing agent instructions may be integration points.

Prefer integration over duplication.

## Required Adoption Plan Contract

A valid proposal must include:

- CURRENT_PAIN
- DESIRED_OUTCOME
- MINIMUM_OAEM_CAPABILITIES_REQUIRED
- EXISTING_PRACTICES_TO_KEEP
- GAPS
- FIRST_VERTICAL_ADOPTION_SLICE
- EVIDENCE_OF_IMPROVEMENT
- ROLLBACK_OR_EXIT_CONDITION
- NEXT_OPTIONAL_CAPABILITY

First slice must solve a real problem.

## Artifact Explosion Prevention

Do not auto-create OAEM scaffolding/document sets.

Avoid automatic creation of:

- `.oaem/` tree
- many policy files
- duplicate roadmaps/status/handoffs
- new ticket/ADR systems without need

Create durable new artifacts only when no existing authority can own the responsibility clearly.

## Composition

- assess-project → adopt-oaem
- adopt-oaem → classify-change → slice-vertically → verify-evidence → checkpoint-work → verify-completion
- handoff-context supports long adoption flows across sessions

## Compliance

- model-agnostic
- harness-agnostic
- project-agnostic
- language-agnostic
