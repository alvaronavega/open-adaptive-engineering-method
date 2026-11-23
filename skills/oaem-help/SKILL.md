---
name: oaem-help
description: Route human or agent questions to minimum sufficient OAEM guidance by identifying intent, loading only relevant authorities/skills, and recommending the smallest safe next flow.
---

# OAEM Help Skill

## Purpose

Provide interactive OAEM guidance for humans or AI agents without requiring prior knowledge of the full skill catalog.

oaem-help is a router/explainer, not a duplicate methodology manual.

## Core Routing Flow

IDENTIFY_INTENT  
→ DISCOVER_RELEVANT_OAEM_AUTHORITY  
→ IDENTIFY_RELEVANT_SKILLS  
→ RECOMMEND_MINIMUM_SUFFICIENT_FLOW  
→ EXPLAIN_WHY_CONCISELY  
→ PROVIDE_NEXT_SAFE_ACTION

## Minimum-Sufficient Rule

Use the minimum sufficient method.

- Trivial question: answer directly.
- Complex/risky question: route to one or more skills.
- Do not force full OAEM lifecycle when not needed.
- Do not impose a rigid mandatory pipeline.

## Skill Routing Examples

- “I have a vague feature idea” → grill-requirement
- “I don’t know whether this needs a spec” → classify-change
- “My repository is confusing” → assess-project → reorganize-existing-project
- “I have too many docs” → audit-documentation
- “A test fails” → diagnose-defect
- “I’m moving to another machine/session” → handoff-context
- “Can I call this done?” → verify-evidence → verify-completion
- “Should I ask a human?” → human-boundary
- “The methodology caused a problem.” → retrospective
- “I think this Skill selected the wrong path.” → retrospective
- “The agent stopped too early.” → retrospective
- “The adapter lost project context.” → retrospective
- “This generated too much documentation.” → retrospective

## Composition Guidance

Recommend multiple skills only when materially useful, for example:

- messy existing project:
  - assess-project
  - reorganize-existing-project
  - audit-documentation

- ambiguous + risky requirement:
  - grill-requirement
  - classify-change
  - human-boundary (if consequential authority is required)

- long autonomous execution:
  - slice-vertically
  - verify-evidence
  - checkpoint-work
  - handoff-context (when context/session changes)

## Explain Key OAEM Concepts On Demand

Should explain concisely when asked:

- DIRECT / TICKET / TEMPORARY_SPEC / GOVERNED_CHANGE
- IMPLEMENTED / VALIDATED / PARTIAL / BLOCKED / HUMAN_REVIEW_REQUIRED / DEFERRED / COMPLETE
- checkpoint vs push
- claim vs evidence
- bounded defect vs human boundary
- canonical vs generated vs historical
- vertical vs horizontal work

## Defect Classification in Guidance

When signals indicate OAEM ecosystem problems, classify candidates as:

- METHOD_DEFECT
- SKILL_DEFECT
- ADAPTER_DEFECT
- HARNESS_DEFECT
- DOCUMENTATION_DEFECT
- ADOPTION_CONFIGURATION_DEFECT

Do not automatically blame the consuming project.

## Source/Loading Discipline

Use progressive loading:

1. oaem-help contract
2. skill catalog / OAEM authorities
3. load only relevant skill details

Do not embed all skill definitions inside oaem-help.

## Human and Agent Outputs

For humans:
- concise recommendation
- rationale
- next safe step

For agents:
- structured next action
- applicable constraints
- minimal required skill sequence

Methodology rules are identical for both.

## Future-Learning Note

If user reports OAEM inconsistency/problem, route to `retrospective` and classify candidate defect type (method/skill/adapter/harness/documentation/adoption configuration) based on available evidence.

Keep oaem-help as a router; do not duplicate retrospective execution logic in this skill.

## Compliance

- model-agnostic
- harness-agnostic
- project-agnostic
- language-agnostic
