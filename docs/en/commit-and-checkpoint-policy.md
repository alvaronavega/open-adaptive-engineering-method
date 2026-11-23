# Commit and Checkpoint Policy (Foundation)

## Purpose

This document distinguishes:

- **Commit policy**: how coherent change intent is represented in Git history.
- **Checkpoint policy**: when evidence is sufficient to preserve validated progress as a commit.

Both are required for reliable autonomous or semi-autonomous engineering loops.

## Source note on conventions

At this stage, only local repository history was available in the current environment (single initial commit).  
No external content was imported.  
Rules below therefore reflect OAEM foundation principles and explicit requested constraints.

## Commit policy (v0.1)

### 1) One coherent intention per commit
Each commit should represent one understandable engineering intention.  
Avoid mixing unrelated intentions in one commit.

### 2) Vertical slices preferred
Default to commits that complete a vertical outcome (behavior + evidence), not broad horizontal layer sweeps.

### 3) Focused evidence before completion checkpoint
A commit intended as completed work should include evidence appropriate to selected depth.

### 4) Failing mandatory gates block COMPLETE status
If required gates fail, do not mark work complete checkpoint; continue bounded correction or escalate.

### 5) Selective staging over blind staging
Prefer curated staging (`git add <paths>`), not blind `git add -A` by default in dirty worktrees.

### 6) Keep unrelated dirty changes out
Unrelated modifications remain outside the commit unless explicitly in scope and justified.

### 7) Push/release is separate authority boundary
Local commit creation does not imply authorized push, release, or deployment.

### 8) Future consistency in technical commit language
Use consistent English commit messaging for future technical history portability.

### 9) Do not rewrite historical commits for cosmetic normalization
Preserve history integrity unless governance explicitly authorizes history rewrite.

## Checkpoint policy (v0.1)

Checkpoint when all are true:
1. slice intention is coherent;
2. required focused validation has passed;
3. mandatory depth gates are not failing;
4. staged diff matches declared scope;
5. checkpoint improves rollback/comparison/regression attribution.

## Why checkpoints matter

Checkpoint commits improve:
- rollback safety;
- before/after comparison;
- regression attribution;
- long-run autonomous execution confidence.

## Local autonomous checkpoint allowance

Project policy may allow local autonomous checkpoint commits for validated slices.  
Publication remains a separate authority step.

## Anti-patterns

- giant mixed-intention commits;
- “checkpoint” commits without evidence;
- bundling unrelated opportunistic edits;
- using commit confidence language while gates fail.

## Related artifacts

- [Checkpoint Policy](checkpoint-policy.md)
- [Completion Contract](completion-contract.md)
- [Evidence Model](evidence-model.md)
- [Human Boundaries](human-boundaries.md)
