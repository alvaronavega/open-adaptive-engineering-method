# Conformance Directory

## Purpose

This directory is for OAEM conformance definitions and validation assets.

Conformance checks whether OAEM method expectations are reproducible and preserved across environments and harnesses.

## What belongs here

- conformance criteria and check definitions;
- reproducibility validation guidance (including fresh-clone expectations);
- cross-harness equivalence checks (future phases);
- regression-oriented method verification assets.

## What does not belong here

- purely stylistic lint-only checks disconnected from method guarantees;
- harness-specific implementation internals with no method relevance;
- generated artifacts not maintained as source of truth.

## v0.1 maturity

Foundation v0.1 establishes conceptual conformance expectations:
- deterministic evidence relevance;
- checkpoint discipline;
- portability invariants;
- fresh-clone reproducibility.

Executable conformance suite implementation is planned for future roadmap phases.

## Future direction

Expected evolution:
- sample-project conformance validation flow;
- cross-harness behavior comparison;
- method regression checks for completion/evidence/boundary handling.

Conformance should validate what OAEM claims, not just what is easy to automate.
