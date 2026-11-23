---
name: slice-vertically
description: Transform an accepted change/outcome into the smallest set of independently verifiable vertical slices, enforcing the vertical by default principle.
---

# Slice Vertically Skill

## Purpose

Decompose an accepted engineering change or outcome into a sequence of minimal, complete, independently verifiable vertical slices.

## Core Principle

**VERTICAL BY DEFAULT.  
HORIZONTAL ONLY BY DEMONSTRATED NECESSITY.**

## Slice Requirements

Each vertical slice must describe:

- OUTCOME: The user or system-visible outcome.
- SCOPE: Boundaries of the slice.
- REQUIRED_LAYERS: Necessary layers involved (UI, domain, storage, tests, etc.)
- ACCEPTANCE_CRITERIA: Clear criteria defining success.
- EVIDENCE_REQUIRED: Evidence needed to prove correctness.
- OUT_OF_SCOPE: Explicitly stated exclusions.
- DEPENDENCIES: Other slices or external dependencies.
- CHECKPOINT_CONDITION: Conditions triggered for a checkpoint.

## Horizontal Exception

Horizontal slicing allowed only with explicit justification:

- WHY_HORIZONTAL: Explanation of why vertical slicing is insufficient.
- BOUNDARY: Defined scope boundary for the horizontal change.
- EXIT_CRITERIA: Criteria indicating when horizontal work ends.
- VERTICAL_OUTCOMES_ENABLED_OR_PROTECTED: Vertical outcomes that are enabled/protected by the horizontal slice.

Without these, horizontal slicing must be rejected or restructured vertically.

## Behavioral Rules

- Avoid manufacturing multiple slices for tiny DIRECT changes.
- Large vertical slices should be split by independently verifiable outcomes.

## Validation Scenarios

- Feature crossing UI/domain/storage/tests → Single vertical slice.
- Multiple independent user outcomes → Multiple vertical slices.
- Change proposing separate sequential phases by model/repository/API/tests → Reject and restructure vertically.
- Shared security migration → Horizontal slice permitted with justification.
- Oversized vertical slice → Split appropriately.
- Tiny direct change → Single slice, no unnecessary splitting.

## Compliance

Maintains model- and harness-agnosticism.

Upholds composability and vertical orientation consistent with OAEM principles.
