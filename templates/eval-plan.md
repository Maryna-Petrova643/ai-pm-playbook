# Eval Plan: <Feature name>

## 1. What "good" means
List the 3–6 quality dimensions that matter most for this feature, derived from real failure modes (not generic metrics like "coherence").

| Dimension | Definition | Why it matters to users |
|---|---|---|
| e.g. Faithfulness | Every claim is supported by the provided context | Wrong answers erode trust fast |

## 2. Golden dataset
- **Size:** 50–100 cases to start; grow to 200–500 before GA; keep adding production failures.
- **Composition:**

| Slice | Share | Examples |
|---|---|---|
| Happy path (common, easy) | ~50% | |
| Edge cases (ambiguous, long, multilingual) | ~25% | |
| Adversarial (prompt injection, jailbreaks, off-topic) | ~15% | |
| Should abstain / escalate | ~10% | |

- **Format:** JSONL, one case per line: `id, input, context, expected, tags`
- **Owner and review cadence:**

## 3. Scoring methods
| Method | Used for | Example |
|---|---|---|
| Code checks (fast, deterministic) | Format, schema, allowed labels, length, PII | JSON parses; label ∈ allowed set |
| Reference match | Checkable answers | Exact category match |
| LLM-as-judge | Subjective quality with a rubric | Tone, faithfulness, helpfulness |
| Human review | Calibration and high-stakes cases | Weekly sample of 30 |

## 4. Judge validation
- Label 50+ cases by hand before trusting the judge.
- Target agreement: ≥ 80% raw agreement or Cohen's kappa ≥ 0.6 per dimension.
- Keep a held-out set of human labels the judge prompt was never tuned on.
- Bias controls: randomize order in pairwise comparisons, control for length, don't judge a model with itself.

## 5. Ship bar
| Metric | Launch bar | Target | Blocking? |
|---|---|---|---|
| Overall pass rate | | | Yes |
| Must-never violations | 0 | 0 | Yes |
| Adversarial slice pass rate | | | Yes |
| p95 latency | | | No |

## 6. When evals run
- Every prompt change: fast suite (code checks + small judged sample)
- Every model change: full golden set + cost/latency comparison
- Pre-release: full set + red-team set + human review
- Production: sampled online scoring with the same judge

## 7. Error analysis loop
1. Review 50–100 failing or sampled outputs; write free-form notes.
2. Group notes into failure categories; count them.
3. Fix the top category (prompt first, then data/context, then model, then architecture).
4. Add new cases for that failure mode to the golden set.
5. Re-run and compare against the previous run.
