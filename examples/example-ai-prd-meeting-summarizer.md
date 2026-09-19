# AI Feature PRD: Meeting Summary & Action Items (worked example)

*Fictional example showing how the template is filled in. Numbers are illustrative.*

| Field | Value |
|---|---|
| Owner | PM, Collaboration team |
| Status | In review |

## 1. Purpose and problem
**Problem:** Team leads spend ~25 minutes after each recurring meeting writing notes and chasing action items (estimate from 12 user interviews). 40% of action items have no clear owner a week later.

**Why now:** Transcription is already on for 70% of meetings; current LLMs summarize long transcripts reliably at under $0.01 per meeting.

**Why AI:** Transcripts are long, unstructured, and messy. Rules can't reliably identify decisions and commitments. AI Feature Fit score: 13/16.

## 2. Users and jobs to be done
| Persona | Job to be done | Current workaround | Pain |
|---|---|---|---|
| Team lead | Share a reliable recap within 10 min | Writes notes by hand | 4 |
| Attendee | Know what I committed to | Scrolls chat, forgets | 3 |

## 3. Goals, non-goals, success metrics
**Goals:** Auto-generate a recap with decisions and owned action items. **Non-goals:** Translating meetings; summarizing meetings without transcripts; auto-creating tasks in third-party tools (v2).

| Metric | Type | Baseline | Launch bar | Target |
|---|---|---|---|---|
| Recap sent within 10 min | User outcome | 22% | 50% | 70% |
| Acceptance (sent with ≤ light edits) | Trust | — | 60% | 75% |
| Golden-set pass rate | Quality | — | 85% | 92% |
| Action items with wrong owner | Guardrail | — | ≤ 5% | ≤ 2% |
| Fabricated decisions | Guardrail | — | 0 in golden set | 0 |
| Cost per meeting | Guardrail | — | ≤ $0.02 | ≤ $0.01 |

## 4. User experience
- Entry: "Generate recap" button appears when a transcript finishes processing.
- Happy path: recap streams in with sections Summary / Decisions / Action items (owner, due date if stated).
- Low confidence: action items with unclear owners show "Owner?" and a picker instead of guessing.
- Fallback: if generation fails, show the transcript with a "Try again" button.
- Controls: edit inline, regenerate, thumbs up/down with reason, "Report a problem."
- Disclosure: "Drafted by AI — review before sending."

## 5. Behavior contract
| Must | Must never | Should |
|---|---|---|
| Only include decisions explicitly stated | Invent owners, dates, or decisions | Keep summary under 150 words |
| Attribute action items to the person who committed | Include content from private side-chats | Use attendees' display names |
| Mark unclear owners as unassigned | Express opinions about participants | Group related action items |

## 8. Evaluation plan (excerpt)
- Golden set: 80 real (consented, anonymized) transcripts: 40 routine, 20 messy/crosstalk, 10 no-decision meetings, 10 adversarial (e.g. someone says "ignore previous instructions").
- Code checks: output parses into the three sections; every owner is an attendee.
- Judge rubric: faithfulness, completeness of action items, owner accuracy. Validated against 50 human-labeled recaps (target kappa ≥ 0.6).

## 10. Rollout
Dogfood (2 weeks) → 10% of teams → 50% → GA. Kill switch: `meeting_recap_enabled` flag. Rollback if any confirmed fabricated decision reaches a customer or acceptance falls below 40%.

## 13. Open questions
- Do we need consent from every attendee before generating a recap?
- Should recaps be editable by all attendees or only the host?
