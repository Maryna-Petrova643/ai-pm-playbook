# AI Metrics Tree

Connect model quality to outcomes the business cares about. If a model metric can't be traced up this tree, question why you're tracking it.

```
North-star business metric (e.g. retained paying users)
│
├── User outcome metrics
│   ├── Task success rate (user got what they came for)
│   ├── Time saved per task
│   ├── Adoption: % of eligible users who try the feature
│   └── Retention: % who use it again within 7 / 30 days
│
├── Trust and experience metrics
│   ├── Acceptance rate (output used as-is or lightly edited)
│   ├── Edit distance / regenerate rate
│   ├── Explicit feedback (thumbs up/down) — a signal, not an eval
│   └── Escalation-to-human rate
│
├── Model quality metrics (offline + sampled online)
│   ├── Golden-set pass rate by slice
│   ├── Faithfulness / hallucination rate
│   ├── Must-never violation count
│   └── Abstention accuracy (declines when it should, answers when it can)
│
└── Operational guardrails
    ├── p50 / p95 latency
    ├── Cost per task and monthly spend
    ├── Error and timeout rate
    └── Rate-limit hits
```

**Warning signs:** eval scores rising while acceptance rate falls means your golden set doesn't match real usage. Refresh it with production samples.
