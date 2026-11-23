# Adapters Directory

## Purpose

This directory holds harness-specific OAEM adapter profiles and guidance.

Adapters translate OAEM core method expectations into harness/runtime-specific execution behavior.

## What belongs here

- adapter profiles per harness;
- harness-specific execution mapping notes;
- constraints/permissions/tooling compatibility documentation;
- conformance notes for preserving OAEM invariants under each harness.

## What does not belong here

- OAEM core method definitions (those belong to methodology/docs);
- hidden auto-generated configs with no source traceability;
- silent mutation logic that rewrites other harness configurations.

## v0.1 maturity

Foundation v0.1 defines adapter responsibilities but does not implement full production adapters yet.

Only generic directional scaffolding is documented to preserve method portability intent.

## Critical invariant

**One harness must not silently mutate another harness configuration.**

Each adapter may own its own:
- executor and tool surface;
- model/provider selection;
- permissions;
- hooks and timeouts;
- output parsing and completion signaling;
- human gate behavior in harness context.

OAEM core owns none of these provider-specific runtime details.
