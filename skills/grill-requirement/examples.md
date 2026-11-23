# Grill Requirement — Validation Scenarios

## 1. Adaptive questioning

- **Input:** “Fix login typo”
- **Observed:** No follow-up questions, interview stops; intent and context are sufficient for DIRECT change.

## 2. Progressive narrowing

- **Input:** “Add checkout payment flow, using Stripe”
- **Observed:**  
  - Initial: Open questions about scope, risk, API, regulatory needs.
  - After confirming Stripe is already used: questions about API version, targeted flows, country constraints disappear.
  - After scoping to single-country, sandbox-only: remaining risk/authority questions narrow to business approval.

## 3. Fact discovery before asking

- **Input:** “Enable free trial on all web projects”
- **Observed:**  
  - Skill discovers all web projects and current subscription architecture before asking for details.
  - Only asks about business rationale, feature toggle needs, and escalation needs.

## 4. Stopping at sufficiency

- **Input:** “Migrate to SSO for all user auth”
- **Observed:**  
  - Skill asks about provider, identity scope, data impact.
  - Stops only when ambiguity is resolved or human authority boundary is confirmed.

## 5. High-risk ambiguity triggers more questions

- **Input:** “Re-architecture for privacy compliance”
- **Observed:**  
  - Progressive layers of questioning on scope, flows, data affected, regulatory drivers.
  - Continues asking until risk and scope are clear enough for TEMPORARY_SPEC or GOVERNED_CHANGE.

## 6. Confirm irrelevant questions disappear

- **Input:** “Fix typo in user settings page”
- **Observed:**  
  - No API/data/infra questions posed; only basic context validation.
