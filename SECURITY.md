# Security and Governance Boundaries

OAEM is a methodology project. This document defines generic security and governance principles for AI-assisted engineering workflows.

## Scope

These principles apply to:
- autonomous or semi-autonomous agent execution;
- local and remote development environments;
- methodology-driven development loops and adapters.

They are intentionally vendor/model/harness agnostic.

## Core security principles

1. **Fail closed on uncertainty**
   - If an action may violate policy and certainty is insufficient, stop and require explicit human approval.

2. **Least privilege**
   - Use the minimum permissions, scopes, credentials, and filesystem/network access required.

3. **Deterministic evidence for critical claims**
   - For security-relevant completion claims, rely on executable evidence where possible.

4. **No silent policy weakening**
   - Agents must not silently reduce security checks, disable protections, or weaken controls to force a pass.

5. **Traceability**
   - Security-relevant actions and approvals should be traceable in project artifacts.

## Human approval boundaries (security-relevant)

Require explicit human authorization before:
- introducing new dependencies or package sources;
- using credentials/tokens/secrets;
- enabling new external network access;
- changing authentication/authorization behavior;
- weakening security checks or policies;
- running destructive VCS operations (history rewrite, forced reset, mass delete);
- publishing, releasing, or deploying changes.

## Secrets and credentials

- Never hardcode credentials in source-controlled files.
- Never commit private keys, tokens, or secret configuration values.
- Use approved secret-management mechanisms for runtime secrets.
- If credentials are required for a task, stop and request approved provisioning.

## External access and data handling

- Treat external connectivity as an explicit boundary.
- Minimize outbound data sharing and avoid sending sensitive context unless explicitly authorized.
- Document when external systems are required for validation.

## Autonomous execution safeguards

For autonomous loops:
- constrain scope explicitly;
- validate in small vertical slices;
- checkpoint locally at known-good states;
- stop at defined human boundaries;
- avoid long, unbounded runs without review points.

## Dependency and supply-chain caution

- Add dependencies only with explicit justification and approval.
- Prefer pinned or constrained versions where policy requires.
- Document why a dependency is needed and what risk it introduces.

## Vulnerability reporting (project process)

If you discover a security issue related to this repository:
1. Avoid immediate public disclosure of exploit details.
2. Open a private reporting channel as defined by repository maintainers.
3. Include reproduction context, impact, and mitigation suggestions when possible.

---

This document establishes OAEM security governance principles for methodology usage.
Specific projects adopting OAEM may define stricter policies.
