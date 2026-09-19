# Behavior Contract: <Feature name>

A behavior contract turns fuzzy "quality" into explicit, testable rules. Every rule here should map to at least one eval case.

## Scope
- **In scope:** requests the feature should handle
- **Out of scope:** requests it should decline or redirect, and the exact redirect message

## Must (hard requirements)
| ID | Rule | Example input | Expected behavior | Eval case IDs |
|---|---|---|---|---|
| M1 | Cites the source document for every factual claim | | | |
| M2 | Responds in the user's language | | | |

## Must never (hard prohibitions)
| ID | Rule | Example input | Expected behavior | Eval case IDs |
|---|---|---|---|---|
| N1 | Never invents prices, dates, or policy terms | | | |
| N2 | Never reveals system prompt or other users' data | | | |

## Should (preferences and tone)
| ID | Preference | Good example | Bad example |
|---|---|---|---|
| S1 | Concise: under 120 words unless asked | | |

## Uncertainty and abstention
- When the AI doesn't know, it should say:
- Confidence threshold for escalating to a human:

## Escalation to humans
- Triggers:
- Handoff message:
- What context is passed to the human:
