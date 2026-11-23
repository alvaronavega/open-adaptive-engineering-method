---
name: classify-change
description: Determine the minimum sufficient OAEM depth by classifying change scope, risk, uncertainty, and impact.
---

# Classify Change Skill

## Purpose

Classify a requested engineering change into the minimum sufficient OAEM depth:
- DIRECT
- TICKET
- TEMPORARY_SPEC
- GOVERNED_CHANGE

## Classification Factors

Evaluate at least:
- scope
- risk
- uncertainty
- blast radius
- reversibility
- security impact
- data impact
- public-contract impact
- architecture impact
- external dependency impact
- required human authority

## Core Principle

SELECT THE MINIMUM SUFFICIENT RIGOR FOR THE REAL RISK.

## Depth Definitions

### DIRECT
- small
- local
- low-risk
- well understood

### TICKET
- bounded change
- clear outcome
- acceptance criteria useful

### TEMPORARY_SPEC
- larger bounded change
- multiple vertical slices
- temporary coordination/documentation needed

### GOVERNED_CHANGE
- architecture
- security
- migration
- data/public contracts
- high-impact irreversible or consequential decisions

## Behavioral Rules

- Do NOT classify primarily by file count.
- Preserve **VERTICAL BY DEFAULT**.
- Favor complete outcomes over technical-layer planning.
- Maintain model-, harness-, and project-independence.

## Validation Scenarios

- typo / tiny localized fix → DIRECT
- medium bounded behavior → TICKET
- multi-slice bounded feature → TEMPORARY_SPEC
- authentication/security architecture change → GOVERNED_CHANGE
- ambiguous cases require explicit rationale
