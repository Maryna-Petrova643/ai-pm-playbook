# AI Feature Fit: Should this be AI?

Score each question 0–2. Total ≥ 10 → strong AI candidate. 6–9 → prototype and test. ≤ 5 → use rules, search, or a better UX first.

| # | Question | 0 | 1 | 2 |
|---|---|---|---|---|
| 1 | Is the input unstructured (text, images, audio, messy data)? | No | Partly | Yes |
| 2 | Would hand-written rules be brittle or endless? | No | Somewhat | Yes |
| 3 | Is an imperfect answer still useful (user can review/edit)? | No | With review | Yes |
| 4 | Is the cost of a mistake low or recoverable? | High | Medium | Low |
| 5 | Can we define "good" clearly enough to evaluate? | No | Roughly | Yes |
| 6 | Do we have (or can we get) representative examples? | No | Few | Many |
| 7 | Does the per-use AI cost fit the value delivered? | No | Unsure | Yes |
| 8 | Is latency acceptable for the user moment? | No | Borderline | Yes |

**Red flags that override the score:** fully automated decisions about money, health, legal status, or employment without human review; no way to evaluate quality; data you're not allowed to send to a model provider.
