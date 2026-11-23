---
name: verify-evidence
description: Determine whether work claims are supported by sufficient, current, and relevant evidence.
---

# Verify Evidence Skill

## Purpose

Determine whether a claim about engineering work is supported by appropriate evidence that is sufficient, current, and relevant to the state being evaluated.

## Core Principle

**EVIDENCE OVER CLAIMS.**

## Evidence Classes

The Skill must distinguish at least:

- DETERMINISTIC_EVIDENCE
- EXECUTION_EVIDENCE
- TEST_EVIDENCE
- BUILD_EVIDENCE
- STATIC_ANALYSIS_EVIDENCE
- SECURITY_EVIDENCE
- DOCUMENTATION_EVIDENCE
- FRESH_CLONE_EVIDENCE
- HUMAN_DECISION
- MODEL_INFERENCE

## Critical Rule

**MODEL CONFIDENCE IS NOT DETERMINISTIC EVIDENCE.**

## Evidence Freshness

Evidence must include enough context to judge relevance:

- PRODUCER: command, action, or process that produced it
- TIME: when it was produced
- STATE: version, checkpoint, or working state it applies to
- SCOPE: what it covers
- RESULT: outcome
- POST_STATE_CHANGE: whether material changes occurred after the evidence was produced

If executable state materially changes after validation, revalidation may be required.

Old evidence must not silently prove a newer changed state.

## Evidence Sufficiency

Required evidence depends on:

- change classification
- adaptive depth
- risk
- applicable project completion contract

Canonical rule:

**USE THE MINIMUM SUFFICIENT EVIDENCE FOR THE CLAIM BEING MADE.**

Do not require every possible evidence type.

## Example Distinctions

- “tests should pass” → CLAIM
- actual test command PASS → TEST_EVIDENCE
- “architecture looks correct” → MODEL_INFERENCE
- explicit human architecture approval → HUMAN_DECISION
- successful build artifact creation → BUILD_EVIDENCE

## Compliance

- model-agnostic
- harness-agnostic
- project-agnostic
- composable with classify-change, slice-vertically, and verify-completion
