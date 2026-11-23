---
name: human-boundary
description: Determine whether execution may continue autonomously or requires explicit human decision.
---

# Human Boundary Skill

## Purpose

Determine whether the current situation allows continued autonomous execution or requires explicit human decision.

## Decision States

- CONTINUE_AUTONOMOUSLY
- HUMAN_DECISION_REQUIRED

## Legitimate Human Boundaries

Examples include:

- NEW_DEPENDENCY
- EXTERNAL_ACCESS
- CREDENTIAL_REQUIRED
- SECURITY_POLICY_CHANGE
- MAJOR_ARCHITECTURE_REPLACEMENT
- DESTRUCTIVE_OPERATION
- RELEASE_OR_PUBLISH
- BUSINESS_OR_PRODUCT_DECISION
- LEGAL_OR_COMPLIANCE_DECISION
- IRREVERSIBLE_HIGH_IMPACT_CHANGE

## Not Normally Human Boundaries

The following are typically bounded engineering defects and should continue autonomously after fix/verification:

- test failure
- compile or typecheck failure
- documentation drift
- bounded parser defect
- local validation script failure
- fixture defect
- bounded regression
- formatting issue
- known implementation defect
- temporary diagnostic failure

## Fail-Closed Rule

If authority for a consequential action cannot be established:

**FAIL CLOSED → HUMAN_DECISION_REQUIRED**

Do not silently assume permission.

## Compliance

- project policy is authoritative
- local checkpoint authority does not imply push or release authority
- model-agnostic
- harness-agnostic
- project-agnostic
