# Generic Adapter Baseline

## Purpose

This directory defines the baseline expectations for a generic OAEM adapter profile.

The generic adapter is a portability reference, not a full harness runtime implementation.

## What belongs here

- method-to-execution mapping guidance that is harness-neutral;
- baseline assumptions for tool usage, evidence reporting, and checkpoint flow;
- conformance expectations that future harness-specific adapters should preserve.

## What does not belong here

- provider-specific model configurations;
- harness-specific private operational details;
- assumptions tied to one IDE, OS, language, or stack.

## v0.1 maturity

At foundation v0.1, this directory is documentation-only.  
No executable adapter implementation is provided yet.

## Future direction

Future generic adapter assets may include:
- normalized completion/evidence signaling conventions;
- compatibility matrix references for harness behaviors;
- minimal baseline adapter profile examples for conformance testing.

All future assets must preserve OAEM invariants:
- adaptive depth behavior;
- vertical by default;
- evidence over claims;
- explicit human boundaries;
- no cross-harness silent configuration mutation.
