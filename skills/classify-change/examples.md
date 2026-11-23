# Classify Change — Validation Scenarios

## DIRECT

- **Scenario:** Typo fix in a single comment or variable
- **Classification:** DIRECT
- **Rationale:** Local, trivial, low-risk, no blast radius

## TICKET

- **Scenario:** Add optional parameter to an existing function with single acceptance criterion
- **Classification:** TICKET
- **Rationale:** Bounded change, acceptance criteria clear, moderate reversibility

## TEMPORARY_SPEC

- **Scenario:** Implement new reporting feature (spans client, server, and API changes), requiring 3 vertical slices and some coordination
- **Classification:** TEMPORARY_SPEC
- **Rationale:** Multi-slice, bounded, needs temporary spec for agreement and coordination

## GOVERNED_CHANGE

- **Scenario:** Migrate user authentication provider and update security protocol across domains
- **Classification:** GOVERNED_CHANGE
- **Rationale:** Architecture/security change, high risk, potentially irreversible, requires human boundary

## AMBIGUOUS/CONDITIONAL

- **Scenario:** Refactor codebase with possible cross-module regressions, unclear system-level impact
- **Classification:** Context-dependent (TEMPORARY_SPEC or GOVERNED_CHANGE)
- **Rationale:** Uncertainty and potential blast radius require explicit rationale, not automatic escalation solely by file count
