# Completion Contract (Foundation)

## Purpose

The completion contract defines when work may be declared complete in OAEM.

It prevents premature stop conditions such as:
- “analysis complete” without implementation;
- “likely fixed” without current validation;
- “pass” claims based on stale evidence.

## Core rule

A task is complete only when the requested outcome and required evidence are both satisfied.

Model confidence or narrative quality cannot replace executable evidence where deterministic verification is possible.

## Foundation completion criteria (v0.1)

At minimum, completion should include:

1. **Outcome satisfied**
   - Requested behavior/artifact exists in the expected scope.

2. **Evidence produced**
   - Validation relevant to risk/depth has been executed in current context.

3. **No blocking deterministic failures**
   - Required gates for the chosen depth are not failing.

4. **Scope integrity preserved**
   - Unrelated changes are not silently bundled as complete work.

5. **Checkpoint readiness**
   - Work is in a coherent state suitable for local checkpoint commit.

## Completion by adaptive depth

| Depth | Minimum completion evidence |
|---|---|
| Level 0 (Direct) | Focused validation proving local intended result |
| Level 1 (Ticket) | Acceptance criteria trace + focused regression |
| Level 2 (Temporary Spec) | Story-by-story evidence + completion trace against temporary spec |
| Level 3 (Governed) | Deterministic gates required by decision artifact + authorized human gate |

## Vertical completion expectation

OAEM completion is vertical by default:
- complete outcome slice;
- integrated where necessary;
- validated;
- evidenced;
- checkpointed.

A horizontal partial layer expansion is not completion unless explicitly scoped and governed as such.

## Defect completion expectation

For defects, completion follows vertical defect closure:
`observed failure → reproduce → first broken contract → smallest sound correction → regression test → affected regression → evidence → checkpoint`

Skipping regression evidence for reproducible defects is not completion.

## Non-completion states

Work should not be reported complete if any of the following is true:
- implementation not applied;
- required validation not executed now;
- failing required gates remain unresolved;
- only model reasoning is provided;
- evidence refers to previous, non-equivalent state;
- pending human boundary decision blocks authorized continuation.

## Relationship to other OAEM artifacts

- [Evidence Model](evidence-model.md): defines evidence classes and reliability.
- [Checkpoint Policy](checkpoint-policy.md): defines when to preserve validated progress.
- [Human Boundaries](human-boundaries.md): defines mandatory escalation boundaries.
- [Adaptive Depth](adaptive-depth.md): defines minimum rigor by change risk.
