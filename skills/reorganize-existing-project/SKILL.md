---
name: reorganize-existing-project
description: Safely reorganize an existing project through inventory, classification, authority consolidation, and vertical cleanup slices while protecting unknowns and unrelated in-progress work.
---

# Reorganize Existing Project Skill

## Purpose

Safely simplify an existing project whose source, docs, generated content, research, vendor material, tests, or agent configuration became hard to understand.

## Canonical Flow

INVENTORY  
→ CLASSIFY  
→ IDENTIFY AUTHORITIES  
→ DETECT OVERLAP / DRIFT  
→ DESIGN TARGET STRUCTURE  
→ MOVE ONE COHERENT VERTICAL SLICE  
→ VALIDATE  
→ CHECKPOINT  
→ CONTINUE

Do not start with broad deletion.

## Classification Contract

Classify relevant content as:

- PRODUCT_SOURCE
- PRODUCT_INTERFACE
- TEST
- FIXTURE
- SKILL_SOURCE
- HARNESS_ADAPTER
- BUILD_TOOLING
- VALIDATION_TOOLING
- DOCUMENTATION_CANONICAL
- DOCUMENTATION_OPERATIONAL
- DOCUMENTATION_HISTORICAL
- DECISION_RECORD
- ROADMAP
- STATUS
- HANDOFF
- GENERATED_BUILD
- GENERATED_RUNTIME
- LOCAL_STATE
- RESEARCH
- SPIKE
- VENDOR
- UPSTREAM
- TEMPORARY
- UNKNOWN

Each item should also get one action recommendation:

- KEEP
- MERGE
- MOVE
- GENERATE
- IGNORE
- ARCHIVE
- DELETE_PROVEN_GENERATED
- SEPARATE_LATER
- REVIEW_REQUIRED

UNKNOWN must never be deleted automatically.

## Authority Overlap Handling

Detect overlapping claims of the same responsibility (status, handoff, roadmap, source ownership, etc.).

Recommend one canonical authority per responsibility.

Do not delete competing artifacts before unique information is preserved.

## Vertical by Default Reorganization

Avoid layer-wide mass moves.

Preferred pattern:

- choose one coherent responsibility slice;
- establish canonical authority;
- move/merge related artifacts only;
- update references;
- validate;
- checkpoint;
- continue.

## Deletion Safety

Deletion requires evidence that target is safely:

- duplicate; or
- generated; or
- obsolete; or
- temporary; or
- preserved elsewhere.

Forbidden by default:

- blind recursive deletion
- `git clean`
- `git reset --hard`
- destructive bulk cleanup for cosmetic git status

unless separately authorized by policy and human authority.

## Existing Change Protection (Dirty Worktree)

Before modifying:

- inspect current git state;
- identify unrelated pre-existing changes;
- isolate proposed reorganization scope;
- preserve unrelated edits.

Use selective staging for checkpoints.

Do not sweep unrelated work into same commit.

## Reproducibility Rule

Reorganization is not complete only because one machine still works.

Evaluate whether an authorized clean environment can reconstruct:

- source
- tests
- skills
- adapters
- fixtures
- configuration
- build/validation surfaces
- handoff/resume state where applicable

Generated output should remain generated, not promoted to canonical source without justification.

## Composition

- assess-project → reorganize-existing-project
- reorganize-existing-project + handoff-context for long restructures
- reorganize-existing-project feeds future audit-documentation work in later batch

## Compliance

- model-agnostic
- harness-agnostic
- project-agnostic
- language-agnostic
