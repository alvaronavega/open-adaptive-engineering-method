# Evidence Model (Foundation)

## Purpose

The OAEM evidence model defines how completion claims are substantiated.

It distinguishes between:
- claim quality (how persuasive a narrative sounds);
- evidence quality (what was actually executed and observed).

Core rule: where deterministic verification is available, deterministic evidence is authoritative.

## Evidence classes (v0.1)

| Class | Description | Reliability |
|---|---|---|
| Deterministic execution evidence | Repeatable command/check output tied to current state | Highest |
| Artifact state evidence | Concrete file/content/state diff that proves requested output exists | High when traceable |
| Reproduction evidence | Repro steps and before/after behavior proving defect closure | High for defect work |
| Exploratory evidence | Manual/heuristic observations without deterministic replay | Useful but limited |
| Model-only claim | Narrative assertion without executable proof | Insufficient when deterministic checks are possible |

## Minimum evidence expectations by depth

| Depth | Minimum expected evidence |
|---|---|
| Level 0 | Focused deterministic check + artifact state confirmation |
| Level 1 | Acceptance coverage + focused regression output |
| Level 2 | Story-level evidence map + completion trace to temporary spec |
| Level 3 | Decision-defined deterministic gates + human gate record |

## Evidence freshness

Evidence must correspond to the current candidate state.

Invalid evidence patterns:
- reusing previous run output after state changed;
- reporting pass from different branch/environment without equivalence;
- claiming unchanged behavior without rerun when affected surfaces changed.

## Evidence for defects

Preferred defect evidence includes:
1. observed failure with reproducible context;
2. correction applied at first broken contract;
3. regression test/check demonstrating closure;
4. affected-path regression confirmation;
5. checkpoint traceability.

## Evidence packaging expectations

When reporting completion, include:
- command/check executed;
- pass/fail result;
- key output or summary;
- scope of what that check covers;
- known uncovered surfaces.

## Relationship to completion contract

The completion contract consumes this model to decide if completion is authorized:
- no required deterministic gate failing;
- no evidence-class downgrade hidden behind confidence language.

See:
- [Completion Contract](completion-contract.md)
- [Checkpoint Policy](checkpoint-policy.md)
- [Continuous Learning](continuous-learning.md)
