# AI Feature PRD: <Feature name>

| Field | Value |
|---|---|
| Owner | |
| Status | Draft / In review / Approved / Shipped |
| Last updated | |
| Reviewers | Eng, Design, Data/ML, Legal/Privacy |
| Related docs | One-pager, eval plan, risk assessment |

## 1. Purpose and problem
**Problem statement:** Who has the problem, what it is, and how often it happens. Include at least one number (baseline or estimate).

**Why now:** What changed (user demand, model capability, cost drop, competitor move).

**Why AI:** Why a deterministic solution isn't enough. Link to the AI Feature Fit score (`frameworks/ai-feature-fit.md`).

## 2. Users and jobs to be done
| Persona | Job to be done | Current workaround | Pain level (1–5) |
|---|---|---|---|

## 3. Goals, non-goals, and success metrics
**Goals:**
**Non-goals:** (explicitly out of scope for this version)

| Metric | Type | Baseline | Launch bar | Target | How measured |
|---|---|---|---|---|---|
| e.g. Task completion rate | User outcome | | | | Product analytics |
| e.g. Eval pass rate on golden set | Model quality | | ≥ 85% | ≥ 92% | Offline eval |
| e.g. Hallucination rate | Guardrail | | ≤ 2% | ≤ 0.5% | Judge + human review |
| e.g. p95 latency | Guardrail | | ≤ 4s | ≤ 2s | Telemetry |
| e.g. Cost per task | Guardrail | | ≤ $0.02 | ≤ $0.01 | Billing logs |

## 4. User experience
Describe every screen, state, and message in plain words. An engineer or AI agent should be able to build from this with zero questions.

- **Entry point:**
- **Happy path:** step by step
- **Loading / streaming state:**
- **Low-confidence state:** what the user sees when the AI isn't sure
- **Error and fallback state:** what happens when the model fails, times out, or refuses
- **User controls:** edit, regenerate, undo, give feedback, report a problem
- **AI disclosure:** how users know AI generated this

## 5. Behavior contract
(Full version: `behavior-contract.md`.)

| The AI must | The AI must never | The AI should (preferences) |
|---|---|---|
| | | |

## 6. Data and context
- **Inputs available to the model:** user data, documents, tools, retrieval sources
- **Data the model must not see:**
- **Freshness requirements:**
- **Retention and logging:** what's stored, for how long, who can access it

## 7. Implementation approach
Prompting / RAG / fine-tuning / agent with tools. Reasoning: see `frameworks/prompt-rag-finetune-build.md`.

- **Candidate models:** (link model selection scorecard)
- **Fallback model or non-AI fallback:**
- **Human-in-the-loop points:**

## 8. Evaluation plan
(Full version: `eval-plan.md`.)
- Golden set size and composition:
- Scoring methods (code checks, LLM judge, human review):
- Ship bar:
- 20 example eval cases: link or inline table

## 9. Risks and mitigations
| Risk | Likelihood | Impact | Mitigation | Owner |
|---|---|---|---|---|
| Hallucinated facts | | | | |
| Prompt injection / misuse | | | | |
| Privacy leak | | | | |
| Bias or unequal quality across user groups | | | | |
| Cost overrun | | | | |

## 10. Rollout and rollback
- **Stages:** internal → beta (x%) → GA
- **Go/no-go criteria per stage:**
- **Kill switch:** who can flip it and how fast
- **Rollback trigger:** the metric thresholds that force a rollback

## 11. Post-launch monitoring
- Online metrics and dashboards
- Sampling rate for human review of production outputs
- How production failures feed back into the golden set

## 12. Timeline and dependencies
| Milestone | Date | Dependency |
|---|---|---|

## 13. Open questions
-
