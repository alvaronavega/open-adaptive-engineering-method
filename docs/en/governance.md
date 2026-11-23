# Governance (Canonical)

## Scope

This is the canonical governance authority for OAEM Foundation v0.1.

It consolidates durable policy expectations for:
- completion and evidence authority;
- commit/checkpoint discipline;
- human authority boundaries;
- language and translation governance;
- harness isolation;
- maturity signaling.

## Completion and evidence authority

Completion is contractual, not rhetorical.

Rules:
- “implemented” is not “completed” by default;
- where deterministic verification exists, deterministic evidence is authoritative;
- model confidence does not override deterministic failure;
- completion state must match available evidence.

Foundation completion states:
- `IMPLEMENTED`
- `VALIDATED`
- `HUMAN_REVIEW_REQUIRED`
- `BLOCKED`
- `DEFERRED`
- `PARTIAL`

## Commit and checkpoint policy

### Commit rules
- one coherent intention per commit;
- vertical slices preferred over broad horizontal sweeps;
- selective staging over blind staging;
- unrelated dirty-worktree changes must stay out of scope commits;
- failing mandatory gates prevent COMPLETE status;
- commit message language should be consistent English technical phrasing;
- checkpoint commit does not imply push/release authority;
- do not rewrite historical commits for style normalization alone.

### Checkpoint rules
Checkpoint when all are true:
1. slice intention is coherent;
2. required focused validation passed;
3. mandatory depth gates are not failing;
4. staged diff matches declared scope;
5. checkpoint improves rollback/comparison/regression attribution.

## Human authority boundaries

Bounded engineering defects should be fixed and execution should continue.

Escalation is mandatory for consequential boundaries (for example):
- new dependencies;
- credentials/secrets;
- external access enablement;
- security-policy weakening;
- destructive operations;
- release/publish/deploy;
- business/product/legal/compliance decisions.

## Language and translation policy

- English is the canonical technical source.
- pt-BR is the official first-class translation.
- EN/PT-BR topology must remain equivalent.
- Translation drift should be detectable through explicit source/translation relationship, without heavy translation machinery in v0.1.

## Harness isolation policy

OAEM core remains independent from provider/runtime details.

Critical invariant:
**One harness must not silently mutate another harness configuration.**

Adapter profiles may vary by harness but must preserve OAEM core invariants.

## Maturity and version signaling

OAEM Foundation v0.1 is experimental and early.

Canonical maturity rule:
**Version numbers represent demonstrated maturity, not the appearance of maturity.**

Breaking changes are expected before 1.0.

## Related authorities

- [Methodology](methodology.md)
- [Getting Started](getting-started.md)
- [Inspirations and Author](inspirations-and-author.md)
- [ROADMAP](../../ROADMAP.md)
- [SECURITY](../../SECURITY.md)
