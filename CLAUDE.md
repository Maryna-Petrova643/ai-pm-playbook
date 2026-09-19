# Instructions for AI agents working in this repo

This repo contains product-management templates for AI features.

When asked to draft a document (PRD, eval plan, one-pager, postmortem, etc.):
1. Find the matching file in `templates/` and follow its section structure exactly. Do not drop sections; write "N/A — reason" if a section doesn't apply.
2. Ask for missing facts rather than inventing numbers. Where an estimate is needed, label it `(estimate)` and state the assumption.
3. For any AI feature, always complete the Behavior Contract and the Eval Plan sections, including at least 20 example eval cases.
4. Save new documents under `docs/<feature-name>/` using kebab-case file names.
5. End every draft with an "Open Questions" list.

Review checklist to run on any draft before returning it:
- [ ] Problem statement contains a number (baseline or estimate)
- [ ] Success metrics have launch / target thresholds
- [ ] Failure modes and fallback behavior are described
- [ ] Rollout and rollback are described (even one line each)
- [ ] Risks include privacy and misuse
