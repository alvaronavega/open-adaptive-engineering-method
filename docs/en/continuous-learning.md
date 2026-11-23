# Continuous Learning (Foundation)

## Purpose

OAEM is intended to improve through real usage, not static theory.

Continuous learning provides a method-level feedback loop that turns observed friction into reproducible improvements and conformance coverage.

## Core loop

`use method → observe friction → reproduce → classify → improve → add regression/conformance coverage → release refined method version`

## Classification categories (v0.1)

Use explicit categories to avoid mixing product bugs with method defects:

- `METHOD_DEFECT`
- `SKILL_DEFECT`
- `ADAPTER_DEFECT`
- `HARNESS_DEFECT`
- `DOCUMENTATION_DEFECT`
- `FALSE_COMPLETION`
- `FALSE_HUMAN_BOUNDARY`
- `MISSING_EVIDENCE`
- `UNNECESSARY_ARTIFACT`
- `CONTEXT_OVERHEAD`
- `CROSS_MACHINE_FAILURE`
- `AGENT_SCOPE_DRIFT`
- `VALIDATION_GAP`

## Classification intent

### Product defect
Issue in the product/system being built.  
May require OAEM process use, but OAEM itself is not necessarily wrong.

### Methodology defect
OAEM rule/design itself causes recurring friction, ambiguity, or unsafe behavior.

### Harness defect
Tool/runtime behavior breaks expected execution portability or evidence integrity.

Clear classification prevents misdirected fixes.

## Feedback quality expectations

Useful learning signals should include:
- concise reproduction context;
- observed behavior vs expected behavior;
- depth level used;
- evidence available/missing;
- whether human boundary handling was appropriate;
- cross-machine/harness factors involved.

## Improvement discipline

When OAEM is changed based on feedback:
1. identify scope of method change;
2. update canonical docs first (English);
3. update first-class translation (pt-BR);
4. add/adjust conformance expectations where practical;
5. record release note/changelog entry.

## Anti-patterns

- “works for me” closure without reproduction;
- relabeling method defects as user error without evidence;
- silent behavior changes without updated method contract;
- adding artifacts that increase overhead without risk reduction.

## Relationship to conformance maturity

At v0.1, conformance is foundational and documentation-heavy.  
Over time, this should evolve toward executable conformance checks and regression suites that validate method behavior across harnesses.

## Related artifacts

- [Problems and Failure Modes](problems-and-failure-modes.md)
- [Evidence Model](evidence-model.md)
- [Harness Portability](harness-portability.md)
- [Checkpoint Policy](checkpoint-policy.md)
