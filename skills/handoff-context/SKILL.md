---
name: handoff-context
description: Create an evidence-grounded OAEM handoff package when context/session/model/harness/machine/human-boundary interruption requires safe continuation by another agent or later session, preserving truthful state without claiming completion.
---

# Handoff Context Skill

## Purpose

Produce a concise, evidence-grounded handoff package that allows another agent, session, model, harness, machine, or human to safely resume work without relying on prior conversation history.

## Critical Invariants

- **HANDOFF != COMPLETE**
- Never upgrade state during handoff.
- A handoff may legitimately report:
  - PARTIAL
  - BLOCKED
  - HUMAN_REVIEW_REQUIRED
  - DEFERRED
  - VALIDATION_FAILING

Repository/project authoritative evidence outranks unsupported narrative claims.

## When to run

Run this skill when one of these conditions is present:

- context window is near exhaustion;
- session is ending;
- model/harness/machine transition is expected;
- human boundary interrupts execution;
- circuit breaker/policy interruption occurs;
- coherent partial work must be preserved;
- user requests continuation later.

Do **not** generate continuous handoffs during normal uninterrupted execution.

## Required Output Contract

Return one structured handoff package containing all fields below.

### 1) Execution state

- CURRENT_STATE
- CURRENT_GOAL
- COMPLETED
- IN_PROGRESS
- NOT_STARTED

### 2) Decisions and constraints

- DECISIONS
- ASSUMPTIONS
- CONSTRAINTS

### 3) Repository/checkpoint state

- CURRENT_BRANCH
- CURRENT_CHECKPOINT
- WORKTREE_STATE

### 4) Evidence and failures

- VALIDATION_EVIDENCE
- KNOWN_FAILURES

### 5) Resume context

- RELEVANT_FILES
- AUTHORITIES_TO_READ
- HUMAN_DECISIONS_PENDING
- DO_NOT_REDO
- DO_NOT_TOUCH
- EXACT_RESUME_POINT
- NEXT_SAFE_ACTION

## Receiver Verification Rule

A receiving agent must:

1. inspect repository/project authorities;
2. verify checkpoint/worktree/current state;
3. verify relevant evidence where needed;
4. correct stale/conflicting claims;
5. only then resume from NEXT_SAFE_ACTION.

If handoff claims conflict with current repository evidence, current evidence wins.

## Composition with OAEM core flow

- partial/interruption state may checkpoint (if authorized) then handoff;
- handoff preserves continuity, never fakes completion;
- resume must rejoin OAEM lifecycle at the verified safe step.

## Minimal format guidance

Use concise bullets or compact sections.
Avoid long prose.
Prefer verifiable statements over interpretation.

## Compliance

- model-agnostic
- harness-agnostic
- project-agnostic
- language-agnostic
- composable with checkpoint-work, verify-evidence, verify-completion, and human-boundary
