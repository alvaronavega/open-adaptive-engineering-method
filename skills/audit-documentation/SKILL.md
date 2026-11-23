---
name: audit-documentation
description: Audit project documentation to detect authority overlap, duplication, contradiction, staleness, and discoverability issues while preserving unique information and minimizing documentation footprint.
---

# Audit Documentation Skill

## Purpose

Identify documentation complexity, duplication, contradiction, staleness, and authority overlap in an existing project.

## Canonical Principle

DOCUMENTATION IS NOT VALUABLE MERELY BECAUSE IT EXISTS.

Target state:

- minimum sufficient documentation
- clear authority
- current information
- easy discovery

## Classification Contract

Classify each relevant document as one or more of:

- CANONICAL
- REFERENCE
- OPERATIONAL
- DECISION
- ROADMAP
- STATUS
- HANDOFF
- HISTORICAL
- GENERATED
- DUPLICATE
- STALE
- OBSOLETE
- UNKNOWN

For each item recommend exactly one action:

- KEEP
- MERGE
- MOVE
- ARCHIVE
- GENERATE
- DELETE
- REVIEW

UNKNOWN must never automatically become DELETE.

## Authority Graph

Map which document owns each durable responsibility, such as:

- project overview
- current status
- current handoff
- architecture
- decisions
- roadmap
- security policy
- development policy
- agent instructions
- operational guidance

Detect and report:

- multiple current status authorities
- multiple current handoff authorities
- contradictory roadmaps
- README duplicating full methodology
- historical docs presented as current
- generated reports treated as canonical authority
- agent instructions contradicting project policy

## Consolidation Rule

A new document requires a responsibility that does not already have an authority.

If existing authority can hold information clearly, update that authority instead of creating another document.

## Preservation and Safety

Before merge/delete/archive decisions:

- identify unique information
- preserve required historical evidence
- update incoming links/references
- distinguish stale assertions from historically meaningful evidence

Do not rewrite history only for cosmetic consistency.

## Complexity Signals (No Universal Score)

Where practical, report:

- total document count
- canonical authority count
- duplicate authorities
- stale documents
- historical documents
- unknown documents
- broken references
- merge proposals
- removal proposals

Do not invent a universal documentation quality score.

## Composition

- assess-project → audit-documentation
- reorganize-existing-project may use audit findings for safe structural work
- oaem-help may route “too many docs / contradictory docs” requests here

## Compliance

- model-agnostic
- harness-agnostic
- project-agnostic
- language-agnostic
