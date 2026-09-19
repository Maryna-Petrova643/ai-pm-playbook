# Choosing an Implementation Approach

Start at the top. Move down only when the level above can't meet the ship bar.

| Approach | Use when | Cost / effort | Watch out for |
|---|---|---|---|
| **1. Prompting** (system prompt + few-shot examples) | Task is general; knowledge fits in the prompt | Lowest; iterate in hours | Prompt sprawl; needs versioning and evals |
| **2. Structured output + tools** | You need reliable JSON or actions (search, DB lookups) | Low–medium | Tool errors; excessive agency |
| **3. RAG** (retrieve relevant documents at runtime) | Answers depend on private or frequently changing knowledge | Medium | Retrieval quality is its own eval; stale indexes |
| **4. Agent / multi-step workflow** | Task needs planning across several steps or tools | Medium–high | Harder to evaluate; compounding errors; cost |
| **5. Fine-tuning** | Consistent style/format at scale, or a narrow task where a smaller model must match a bigger one | High | Needs lots of quality data; goes stale; retraining cost |
| **6. Train your own model** | Rarely justified for product teams | Very high | Almost always the wrong first move |

**Rule of thumb:** Most failures are fixed by a better prompt or better context, not a new model. Try prompt → context/data → model swap → architecture change, in that order.
