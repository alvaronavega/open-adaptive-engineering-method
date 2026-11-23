---
name: assess-project
description: Assess an existing project in read-only mode before adoption, reorganization, or consequential changes by separating observed facts, claims, inferences, unknowns, contradictions, and required human decisions.
---

# Assess Project Skill

## Purpose

Build an evidence-grounded understanding of an existing project before recommending OAEM adoption, reorganization, or consequential actions.

## Default Authorization

READ-ONLY by default.

Do not, unless explicitly authorized:

- move/delete files;
- edit configuration;
- install dependencies;
- rewrite documentation;
- clean git state;
- commit;
- push.

Assessment first. Changes later.

## Assessment Scope

Inspect what exists before asking humans.

Assess, when present:

- PROJECT PURPOSE
- CURRENT MATURITY
- TECHNOLOGY STACK
- REPOSITORY STRUCTURE
- SOURCE LOCATIONS
- TEST LOCATIONS
- BUILD/VALIDATION COMMANDS
- DOCUMENTATION AUTHORITIES
- DECISION RECORDS
- CURRENT STATUS / HANDOFF
- SKILLS / AGENT INSTRUCTIONS
- HARNESS CONFIGURATION
- GENERATED CONTENT
- RUNTIME CONTENT
- RESEARCH / SPIKES
- VENDOR / UPSTREAM
- GIT STATE
- FRESH-CLONE EXPECTATIONS
- KNOWN RISKS / BLOCKERS
- EXISTING DEVELOPMENT METHOD

Absence is information, not automatically a defect.

## Evidence Typing Contract

Every relevant statement should be typed as one of:

- OBSERVED_FACT
- DOCUMENTED_CLAIM
- INFERENCE
- ASSUMPTION
- UNKNOWN
- CONTRADICTION
- HUMAN_DECISION_REQUIRED

Do not present INFERENCE/ASSUMPTION as OBSERVED_FACT.

## Human Interaction Rule

Ask humans only after repository/project discovery cannot resolve material unknowns or contradictions.

Use progressive requirement discovery when unresolved questions can change next engineering decisions.

## Output Contract (Concise)

Return a concise assessment including:

- PROJECT_SUMMARY
- AUTHORITATIVE_SOURCES
- REPOSITORY_MAP
- CURRENT_WORKFLOW
- VALIDATION_SURFACES
- DOCUMENTATION_AUTHORITIES
- SOURCE/GENERATED/HISTORY/RESEARCH/VENDOR BOUNDARIES
- REPRODUCIBILITY_STATUS
- RISKS
- CONTRADICTIONS
- UNKNOWN_INFORMATION
- HUMAN_DECISIONS_NEEDED
- SAFE_NEXT_ACTION

Avoid giant default reports.

## Composition

- assess-project → adopt-oaem
- assess-project → reorganize-existing-project
- assess-project + handoff-context for long analyses or context interruption

## Compliance

- model-agnostic
- harness-agnostic
- project-agnostic
- language-agnostic
