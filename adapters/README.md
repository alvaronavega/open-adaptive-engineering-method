# Adapters Directory

## Purpose

This directory defines OAEM harness-adapter contracts.

Adapters map OAEM methodology behavior into harness/runtime execution behavior while keeping OAEM core provider-neutral.

## Critical invariants

- One harness must not silently mutate another harness configuration.
- OAEM core must not embed provider-specific runtime configuration.
- Adapter maturity must be declared honestly (no fake operational claims).

## Generic adapter contract (minimum)

Any OAEM-consuming harness should define how it handles:

- OAEM Skill discovery
- project authority discovery
- context loading strategy
- skill executor/invocation mechanism
- tool surface and permissions
- human-boundary signaling and approval path
- checkpoint authority
- push authority
- release authority
- timeout/circuit-breaker behavior
- completion signals
- handoff/resume behavior
- result normalization
- evidence capture

This contract is conceptual and integration-oriented, not a runtime framework implementation.

## Harness isolation requirements

Each adapter/profile owns its own:

- executor
- model/provider selection
- tools
- permissions
- environment assumptions
- flags
- limits/timeouts
- output handling
- continuation behavior
- human-approval behavior

Cross-harness silent mutation is forbidden.

## Adapter representations (initial)

| Adapter | Maturity | Notes |
|---|---|---|
| generic | CONTRACT_DEFINED | Baseline harness-neutral contract reference. |
| Ralph | PILOT_REQUIRED | OAEM integration boundary defined; operational verification pending pilot. |
| Axet | PILOT_REQUIRED | Skill-driven integration expected; executor behavior unverified. |
| Codex | PILOT_REQUIRED | Contractual mapping only; no operational validation evidence yet. |
| Claude | PILOT_REQUIRED | Contractual mapping only; no operational validation evidence yet. |
| Copilot | PILOT_REQUIRED | Contractual mapping only; no operational validation evidence yet. |
| Gemini | PILOT_REQUIRED | Contractual mapping only; no operational validation evidence yet. |

Allowed maturity states:
- CONTRACT_DEFINED
- PILOT_REQUIRED
- EXECUTOR_UNVERIFIED
- NOT_YET_IMPLEMENTED
- OPERATIONALLY_VALIDATED

Use `OPERATIONALLY_VALIDATED` only with explicit real evidence.

## Ralph integration boundary (contractual)

OAEM expects Ralph integration to map:

- story/slice decomposition to OAEM vertical slices;
- checkpoint behavior distinct from push/release;
- completion behavior with fail-closed contract;
- human-boundary behavior for consequential decisions;
- handoff behavior across context/session/machine changes;
- retrospective feedback capture for learning loop.

Ralph operational implementation remains harness-specific and out of OAEM core scope.

## v0.1 / pre-pilot posture

Adapters are represented contractually for pilot readiness.
Operational validation is deferred to real-project pilots.
