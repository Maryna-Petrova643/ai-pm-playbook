# Rollout and Rollback Plan: <Feature name>

| Stage | Audience | Duration | Exit criteria | Owner |
|---|---|---|---|---|
| 0. Dogfood | Internal team | 1 week | No blocking bugs; eval ≥ launch bar | |
| 1. Beta | 5% or opt-in users | 2 weeks | Guardrail metrics within bounds | |
| 2. Expansion | 25–50% | 1–2 weeks | Primary metric trending positive | |
| 3. GA | 100% | — | — | |

## Kill switch
- Mechanism (feature flag name):
- Who can flip it:
- Expected time to disable:
- What users see when disabled:

## Automatic rollback triggers
| Metric | Threshold | Window |
|---|---|---|
| Error / timeout rate | > x% | 15 min |
| Must-never violations detected | ≥ 1 confirmed | Any |
| Cost per task | > 2× budget | 1 hour |
| User complaint rate | > x% | 1 day |

## Model or prompt changes after launch
Every change goes through the eval suite and a staged rollout, same as a code release.
