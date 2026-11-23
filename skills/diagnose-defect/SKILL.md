---
name: diagnose-defect
description: Identify the first broken contract when failure occurs and drive the smallest sound correction.
---

# Diagnose Defect Skill

## Purpose

Locate and address the first contract breach when implementation or validation fails, driving the smallest correction necessary to restore function.

## Diagnostic Flow

1. **FAILURE**: Detect when a failure occurs.
2. **REPRODUCE**: Attempt to reproduce the failure.
3. **GATHER EVIDENCE**: Collect all relevant evidence.
4. **TRACE BOUNDARIES**: Define the scope of failure.
5. **IDENTIFY FIRST BROKEN CONTRACT**: Find the earliest contract that was breached.
6. **FIX SMALLEST SOUND LAYER**: Correct at the lowest responsible layer.
7. **FOCUSED VALIDATION**: Validate that the fix resolves the issue.
8. **AFFECTED REGRESSION**: Check for any regressions introduced by the fix.
9. **RETURN TO EVIDENCE VERIFICATION**: Loop back and ensure all evidence aligns.

## Rules for Diagnosis

- **SYMPTOM**: Observable issue.
- **ROOT_CAUSE**: Underlying problem causing the symptom.
- **FAILED_BOUNDARY**: Point where the expected behavior diverged.
- **SPECULATIVE_HYPOTHESIS**: Unvalidated assumption about the cause.
- **PROVEN_CAUSE**: Confirmed explanation for the problem.
- **FIX**: Applied correction.
- **REGRESSION_EVIDENCE**: Verification that the fix didn't introduce new issues.

## Critical Avoidances

- Avoid patching superficial symptoms when deeper issues exist.
- Avoid speculative fixes without evidence.
- Avoid weakening tests to bypass issues.
- Avoid hardcoding to circumvent validation.
- Avoid large refactorings that aren't necessary for the fix.

## Compliance

- Model-agnostic
- Harness-agnostic
- Project-agnostic

## Validation Scenarios

- Failing test linked to product behavior change → investigate product contract.
- Diagnostic query failure → enhance diagnostics and proceed.
- Outdated test expectations → update accordingly with evidence.

## Composition

Works within overall OAEM flow, integrating with skills like verify-evidence and slice-vertically.
