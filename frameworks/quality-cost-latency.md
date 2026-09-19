# Quality × Cost × Latency Tradeoffs

Every AI feature trades these three against each other. Make the tradeoff explicit instead of discovering it after launch.

## 1. Set the budget per user moment
| User moment | Latency tolerance | Quality tolerance | Example |
|---|---|---|---|
| Inline / as-you-type | < 500 ms | Medium | Autocomplete |
| Interactive answer | 1–5 s (stream it) | High | Chat assistant |
| Background job | Minutes | Very high | Report generation |

## 2. Levers
| Lever | Improves | Costs |
|---|---|---|
| Bigger / smarter model | Quality | Cost, latency |
| Smaller / faster model | Cost, latency | Quality (test it!) |
| Model routing (easy → small, hard → big) | Cost | Complexity; routing errors |
| Caching repeated prompts/results | Cost, latency | Staleness |
| Shorter prompts / less context | Cost, latency | May lose accuracy |
| Streaming output | Perceived latency | None really |
| Batch processing | Cost | Latency |

## 3. Unit economics check
`Cost per task × tasks per user per month` must fit comfortably inside `revenue per user per month × target AI cost share` (often 10–30%).
