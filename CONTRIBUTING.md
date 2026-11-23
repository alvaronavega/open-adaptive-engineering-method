# Contributing to OAEM

Thank you for your interest in improving OAEM.

OAEM is an open methodology project. Contributions should strengthen method clarity, reproducibility, governance, and cross-harness portability.

## Scope of contributions

High-value contributions include:
- methodology clarifications and refinements;
- failure mode documentation improvements;
- evidence and completion contract proposals;
- adapter contract proposals (without coupling OAEM core to vendors);
- conformance and reproducibility criteria;
- translation quality improvements (English canonical + pt-BR synchronized translation).

## Contribution principles

1. **Methodology first**
   - Keep OAEM positioned as a software engineering methodology.
   - Avoid coupling the OAEM core to any specific model, harness, vendor, IDE, or programming language.

2. **Evidence over claims**
   - Proposals should include rationale and, when applicable, deterministic validation evidence.

3. **Adaptive depth**
   - Avoid one-size-fits-all documentation burden.
   - Propose the minimum sufficient artifact depth for the risk involved.

4. **Respect harness isolation**
   - Do not design changes that require one harness to mutate another harness configuration.

5. **No hidden assumptions**
   - If a workflow depends on scripts, files, or fixtures, they must be committed and documented.

## Language policy

- Canonical technical source: `README.md` and `docs/en/**`.
- Official first-class translation: `README.pt-BR.md` and `docs/pt-BR/**`.
- Do not mix languages inside the same technical document.
- Keep translation parity traceable (see docs on synchronization policy).

## Pull request expectations

When opening a PR:
- explain the problem being addressed;
- classify whether it is a methodology, skill, adapter, harness, documentation, or conformance issue;
- describe expected impact and non-goals;
- list validation performed;
- identify any human-boundary implications (if any).

Recommended PR checklist:
- [ ] OAEM core remains model/harness/vendor agnostic.
- [ ] Terminology is consistent with existing docs.
- [ ] Links are valid and relative paths resolve.
- [ ] English and pt-BR docs remain synchronized where applicable.
- [ ] No unsupported maturity claims were introduced.
- [ ] No hidden dependency or local-state assumptions were introduced.

## Code of conduct

By participating, you agree to follow [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md).

## Security considerations

For security-sensitive issues, follow [SECURITY.md](SECURITY.md) rather than public disclosure first.
