---
name: verify-completion
description: Determine whether a slice or change may legitimately be considered complete under OAEM.
---

# Verify Completion Skill

## Purpose

Determine whether a vertical slice or change may legitimately be considered complete.

## Core Rule

Completion is not:
- agent confidence
- summary wording
- “looks done”
- old validation evidence
- partially implemented plans

Completion evaluates:
- required outcome
- acceptance criteria
- required evidence
- mandatory gates
- open defects
- human boundaries
- checkpoint state
- scope coherence

## Foundation Completion States

- IMPLEMENTED
- VALIDATED
- PARTIAL
- BLOCKED
- HUMAN_REVIEW_REQUIRED
- DEFERRED
- COMPLETE

## State Rules

- IMPLEMENTED != COMPLETE
- VALIDATED does not automatically imply COMPLETE if acceptance criteria remain open
- mandatory failing gate forbids COMPLETE
- missing required human decision yields HUMAN_REVIEW_REQUIRED
- intentionally postponed approved work yields DEFERRED
- unfinished required outcome yields PARTIAL

## Completion Contract

A slice or change may reach COMPLETE only when all are true:

- required outcome exists
- acceptance criteria are satisfied
- required evidence is sufficient and current
- mandatory gates pass
- no unresolved blocking defect exists
- required human decisions are satisfied
- scope is coherent
- checkpoint requirements are satisfied where applicable

Otherwise completion must fail closed.

## Compliance

- model-agnostic
- harness-agnostic
- composable with classify-change, slice-vertically, and verify-evidence
- preserves minimum sufficient rigor and fail-closed completion behavior
