# Human Boundaries (Foundation)

## Purpose

Human boundaries define when autonomous execution must stop and request explicit human decision authority.

This prevents two common failures:
- unnecessary escalation of normal bounded engineering defects;
- unauthorized execution of consequential decisions.

## Core distinction

OAEM separates:

1. **Ordinary bounded defect**  
   Agent should fix and continue within approved scope.

2. **Real human boundary**  
   Agent must stop and obtain explicit authorization before proceeding.

## Ordinary bounded defects (continue autonomously)

Examples:
- test failure caused by current change;
- parser/type/format errors in local work scope;
- documentation drift introduced by current edits;
- bounded regression repair in directly affected surfaces;
- local script/tooling defect that can be corrected safely.

Rule: if fix is technically bounded and does not cross authority boundaries, continue.

## Real human boundaries (must escalate)

Examples include:
- adding new dependency or package source;
- requiring credentials/secrets or privileged access;
- enabling new external network/system access;
- weakening security policy or controls;
- destructive version-control actions;
- major architecture replacement beyond approved scope;
- release/publish/deploy actions;
- business/product tradeoff decisions.

Rule: stop, state boundary reason, request explicit decision.

## Escalation payload expectations

When escalation is required, provide:
- boundary category;
- why continuation crosses authority;
- options with risks and consequences;
- recommended option and rationale;
- minimal information needed for decision.

## Anti-patterns

Do not escalate because of:
- “it might be difficult”;
- “tests failed once”;
- “I found an implementation bug”;
- “documentation needs updates”.

These are normal engineering work unless they cross a real authority boundary.

## Relationship with completion and evidence

If a human boundary blocks continuation:
- do not report COMPLETE;
- report boundary status explicitly;
- preserve any validated progress as bounded checkpoint if policy allows.

See:
- [Completion Contract](completion-contract.md)
- [Evidence Model](evidence-model.md)
- [Security and Governance Boundaries](../../SECURITY.md)
