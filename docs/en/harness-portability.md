# Harness Portability (Foundation)

## Purpose

OAEM is harness-agnostic at the methodology core.

Harness portability defines how OAEM remains consistent across different agent runtimes without forcing a single universal harness configuration.

## Core rule

Use:
- one shared methodology contract;

plus:
- isolated harness adapters/profiles.

Do not let one harness silently mutate another harness configuration.

## Why this matters

Different harnesses vary in:
- available tools and execution commands;
- permission models;
- output format and verbosity;
- retry/timeout behavior;
- filesystem and sandbox constraints;
- hook and automation semantics.

Without explicit isolation, cross-harness drift undermines reproducibility and trust.

## OAEM portability model (v0.1)

1. **Method core remains stable**
   - Principles, evidence rules, completion logic, and human boundaries stay method-level.

2. **Adapter layer maps harness behavior**
   - Adapter profiles define harness-specific execution details while preserving method intent.

3. **Conformance checks validate equivalence**
   - Different harnesses should satisfy equivalent completion/evidence outcomes for equivalent tasks.

4. **Mutation boundaries are explicit**
   - Harness-specific local configuration must not be auto-rewritten by another harness workflow.

## Portability invariants

Portability should preserve at least:
- adaptive depth behavior;
- vertical-by-default execution intent;
- evidence-over-claims rule;
- human boundary escalation requirements;
- checkpoint discipline.

If these invariants break, portability is degraded even if output appears superficially similar.

## Fresh-clone perspective

Harness portability should be evaluated from fresh-clone assumptions:
- required assets tracked in repository;
- required scripts/config documented;
- no hidden local state required for baseline operation.

See [Continuous Learning](continuous-learning.md) for classification of cross-machine failures.

## Anti-patterns

- embedding harness-specific assumptions into OAEM core definitions;
- hidden adapter generation with no source control traceability;
- silent profile rewrites across harness ecosystems;
- claiming portability without conformance evidence.

## Related artifacts

- [Methodology Overview](methodology-overview.md)
- [Completion Contract](completion-contract.md)
- [Evidence Model](evidence-model.md)
- [Continuous Learning](continuous-learning.md)
