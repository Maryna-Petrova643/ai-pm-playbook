# AI PM Playbook

A working toolkit of templates and frameworks for product managers shipping AI and LLM features.

Traditional PRDs assume deterministic software: same input, same output, pass/fail acceptance criteria. AI features break that assumption. Quality is a distribution, failures don't throw errors, and "done" means "good enough on a golden set we agreed on before building." Every template here is designed around that reality.

## How to use this repo

1. **Deciding whether to build with AI at all?** Start with `frameworks/ai-feature-fit.md`.
2. **Scoping a feature?** Copy `templates/ai-prd.md`. Fill in the Behavior Contract and Eval Plan *before* engineering starts.
3. **Choosing a model or vendor?** Use `templates/model-selection-scorecard.md`.
4. **Getting ready to ship?** Work through `templates/launch-checklist.md` and `templates/rollout-rollback-plan.md`.
5. **Something went wrong in production?** `templates/incident-postmortem.md`.

## Structure

```
ai-pm-playbook/
├── CLAUDE.md                          # Lets Claude Code / agents draft docs from these templates
├── templates/
│   ├── ai-prd.md                      # Full PRD for an AI feature (with behavior contract + evals)
│   ├── one-pager.md                   # Pitch an idea in one page before writing a PRD
│   ├── behavior-contract.md           # What the AI must / must never / should do
│   ├── eval-plan.md                   # Golden set, metrics, ship bar, judge validation
│   ├── model-selection-scorecard.md   # Compare models/vendors on your own tasks
│   ├── ai-risk-assessment.md          # Harms, misuse, privacy, compliance
│   ├── experiment-brief.md            # A/B tests and prompt experiments
│   ├── launch-checklist.md            # Go / no-go gates
│   ├── rollout-rollback-plan.md       # Staged release + kill switch
│   ├── incident-postmortem.md         # Blameless AI incident review
│   ├── stakeholder-update.md          # Weekly/biweekly status note
│   └── decision-log.md                # Record of key product decisions
├── frameworks/
│   ├── ai-feature-fit.md              # Should this be AI? Scoring rubric
│   ├── prompt-rag-finetune-build.md   # Choosing an implementation approach
│   ├── ai-metrics-tree.md             # Linking model quality to business outcomes
│   └── quality-cost-latency.md        # Making tradeoffs explicit
└── examples/
    └── example-ai-prd-meeting-summarizer.md
```

## Principles

- **Evals are the spec.** If you can't say what "good" looks like on 50 representative cases, the feature isn't ready for engineering.
- **Define the ship bar before the build.** Launch thresholds agreed up front prevent goalpost-moving later.
- **Plan for failure.** Every AI feature needs a fallback, a human escalation path, and a kill switch.
- **Measure what users feel.** Model scores must tie back to user and business metrics, or they're vanity numbers.
- **Write for humans and agents.** These templates are plain Markdown so an AI coding agent can read and fill them.

## License

MIT. Use, fork, and adapt freely.
