---
name: retrospective
description: Convert execution experience into evidence-grounded reusable learning by distinguishing product, method, skill, adapter, harness, documentation, adoption, validation, environment, and human-decision defects without premature methodology churn.
---

# Retrospective Skill

## Purpose

Convert practical execution experience into actionable, evidence-grounded improvements without confusing product defects with OAEM method/skill/harness defects.

Retrospective is a learning mechanism, not a status summary.

## Core Questions

A retrospective should answer:

- WHAT_WAS_INTENDED
- WHAT_ACTUALLY_HAPPENED
- WHAT_EVIDENCE_SUPPORTS_THIS_ACCOUNT
- WHAT_WORKED
- WHAT_CREATED_FRICTION
- WHAT_FAILED
- WHERE_WAS_FIRST_BROKEN_CONTRACT
- DEFECT_CLASSIFICATION_PRIMARY
- WHAT_SHOULD_CHANGE
- WHAT_SHOULD_REMAIN_UNCHANGED
- WHAT_CONFORMANCE_OR_REGRESSION_EVIDENCE_SHOULD_BE_ADDED

## Not a Status Report

Do not stop at:

- files changed
- tests passed
- commit created
- task completed

Extract reusable learning and contract-level implications.

## Trigger Guidance

Run retrospective when justified, including:

- completed vertical slice with meaningful learning;
- failed/blocked slice;
- false completion;
- false human boundary;
- human intervention event;
- context exhaustion/cross-session recovery;
- cross-machine failure;
- skill selection/routing failure;
- adapter/harness failure;
- unnecessary documentation growth;
- fresh-clone failure;
- scope drift;
- successful reusable experiment.

Do not require retrospective after every trivial DIRECT change.

## Primary Classification Model

Assign exactly one primary category:

- PRODUCT_DEFECT
- METHOD_DEFECT
- SKILL_DEFECT
- ADAPTER_DEFECT
- HARNESS_DEFECT
- DOCUMENTATION_DEFECT
- ADOPTION_CONFIGURATION_DEFECT
- VALIDATION_DEFECT
- ENVIRONMENT_DEFECT
- HUMAN_DECISION_GAP
- UNKNOWN

Secondary categories are optional when they improve action quality.

UNKNOWN must remain honest when evidence is insufficient.

## Evidence Contract

Each finding should separate:

- OBSERVED_BEHAVIOR
- REPRODUCTION
- EXPECTED_BEHAVIOR
- ACTUAL_BEHAVIOR
- EVIDENCE
- IMPACT
- ROOT_CAUSE_STATUS: PROVEN | HYPOTHESIS | UNKNOWN

Do not present hypothesis as proven root cause.

## Learning Decision Model

For each finding choose one action:

- NO_CHANGE
- CLARIFY_EXISTING_AUTHORITY
- UPDATE_SKILL
- UPDATE_METHOD
- UPDATE_ADAPTER
- UPDATE_HARNESS
- ADD_CONFORMANCE_SCENARIO
- ADD_REGRESSION_TEST
- CHANGE_ADOPTION_CONFIGURATION
- RUN_EXPERIMENT
- HUMAN_REVIEW_REQUIRED
- DEFER

Do not auto-create new docs/skills for every finding.

## Change Threshold

Immediate change may be justified when:

- defect is reproducible; and
- impact is material; and
- correction is low-risk and contract-improving; or
- a core safety/completion invariant is violated.

Otherwise prefer:

record → observe recurrence → bounded experiment → collect evidence → deliberate change.

Avoid methodology churn from isolated preference.

## Positive Learning Requirement

Capture what worked, not only failures (examples: effective vertical slicing, safe checkpoint use, productive requirement discovery, useful fresh-clone detection, correct human-boundary enforcement).

## Implementation Feedback Loop

USE OAEM  
→ OBSERVE  
→ CAPTURE EVIDENCE  
→ CLASSIFY  
→ DECIDE ACTION  
→ IMPROVE  
→ ADD CONFORMANCE/REGRESSION EVIDENCE  
→ RELEASE IN FUTURE VERSION  
→ OBSERVE AGAIN

Do not imply every retrospective changes published method version immediately.

## Handoff Integration

If work ends before retrospective closes:

handoff-context should preserve:

- known observations
- unresolved classification
- evidence locations
- exact next learning action

Do not claim learning complete while classification remains uncertain.

## Composition

- oaem-help routes methodology/skill/harness/adapter confusion to retrospective
- retrospective findings may drive updates in core/adoption skills and conformance assets
- retrospective may trigger human-boundary when consequential governance change is required

## Compliance

- model-agnostic
- harness-agnostic
- project-agnostic
- language-agnostic
