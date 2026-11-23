# Checkpoint Policy (Foundation)

## Purpose

Checkpoint policy defines when and why OAEM preserves progress as a coherent local commit boundary.

Checkpoints are not just “save points.”  
They are evidence-linked control points for rollback, comparison, and regression attribution.

## Core rule

Checkpoint coherent progress, not arbitrary partial motion.

A checkpoint should represent one coherent intention with evidence appropriate to selected depth.

## What makes a valid checkpoint

A checkpoint is valid when all are true:

1. The slice has a clear intention.
2. Required focused validation for that slice has passed.
3. Mandatory deterministic gates for selected depth are not failing.
4. Unrelated workspace changes are excluded.
5. The checkpoint can be understood independently by reviewer/future agent.

## Vertical checkpoint preference

OAEM is vertical by default.  
Checkpoint policy follows the same rule:
- prefer completed vertical slice checkpoints;
- avoid large horizontal accumulation before first safe preservation.

## Defect checkpoints

Preferred defect checkpoint sequence:
`observed failure → reproduce → smallest sound fix → regression evidence → checkpoint`

Avoid combining unrelated refactors in the same defect checkpoint.

## Checkpoint vs push/release authority

Checkpointing and publication are different authority boundaries:

- **Checkpoint (local)**: preserves validated progress.
- **Push/release**: project authority boundary and may require additional approvals.

A valid local checkpoint does not imply automatic publish authorization.

## Mandatory gate behavior

If required gates fail at the chosen depth:
- do not report complete;
- do not checkpoint as completed slice;
- either continue bounded correction or escalate by policy.

## Staging discipline

Checkpoint quality depends on selective staging:
- include only files related to current coherent intention;
- exclude unrelated dirty-worktree changes;
- avoid blind staging as default behavior.

## Historical stability principle

Use consistent commit policy for future commits, but do not rewrite historical commits only for cosmetic normalization unless governance explicitly authorizes history rewriting.

## Related artifacts

- [Commit and Checkpoint Policy](commit-and-checkpoint-policy.md)
- [Completion Contract](completion-contract.md)
- [Evidence Model](evidence-model.md)
