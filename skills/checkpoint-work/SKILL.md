---
name: checkpoint-work
description: Preserve a coherent validated development slice to enable safe autonomous continuation, separating checkpoint from push and release authority.
---

# Checkpoint Work Skill

## Purpose

Preserve a coherent, validated development slice so an autonomous agent can continue without accumulating unsafe unbounded diffs.

## Checkpoint Elements

A checkpoint should capture and declare:

- COHERENT_INTENT: Clear scope and purpose of the checkpoint.
- SCOPE: Boundaries of contained changes.
- EVIDENCE: Required and fulfilled evidence supporting changes.
- VALIDATION_STATE: Overall status of validations and gates.
- KNOWN_LIMITATIONS: Explicitly acknowledged incomplete or deferred aspects.
- REMAINING_WORK: Outstanding tasks beyond the checkpoint.
- RESUME_POINT: Logical point to continue work.

## Distinctions

- Checkpoint authority is local and does NOT imply push or release authority.
- Push authority and release authority are distinct from checkpoint authority.

## Checkpoint Requirements

A completion-style checkpoint should have:

- Coherent vertical slice.
- Appropriate evidence satisfied.
- Mandatory gates not failing.
- Staged diff limited to checkpoint scope.
- Clear intent labeling.
- Honest reporting of known failures or limitations.

A recovery checkpoint is allowed when:

- Context is exhausted.
- Environmental interruption occurs.
- A human boundary is reached.

Recovery checkpoints must NOT claim COMPLETE status.

## Dirty Worktree Handling

- Inspect current working state for unrelated changes.
- Selectively stage checkpoint-owned changes only.
- Avoid blind staging (e.g., `git add -A`).
- Do not revert or hide unrelated files solely to achieve cleaner status.

## Failure Handling

If checkpoint validation fails:

- Do not create a completion checkpoint claiming success.
- Return to diagnose-defect → fix → verify-evidence → verify-completion loop.
- Unless a real human boundary exists.

## Compliance

- Model-agnostic
- Harness-agnostic
- Project-agnostic
- Composable with classify-change, slice-vertically, verify-evidence, verify-completion, diagnose-defect, and human-boundary skills.
