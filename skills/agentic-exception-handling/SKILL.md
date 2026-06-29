---
name: agentic-exception-handling
description: Makes agents robust to the failures real environments throw at them — tool errors, API failures, network issues, invalid data, timeouts. Combines proactive detection with reactive handling (retry, fallback, graceful degradation) and recovery (revert to a stable state, self-correct, or escalate). Use for any agent deployed where failures are possible and reliability matters.
---

# Exception Handling and Recovery

> Agentic Design Pattern 12 of 21 — distilled from Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems* (Ch. 12).

**What it is.** Anticipate failure points and respond systematically: detect (validate tool outputs, check error codes, use timeouts), handle (log, retry, fall back, degrade gracefully, notify), and recover (diagnose, self-correct the plan, or escalate to a human).

## Reach for this when
- An agent runs in a dynamic, real-world environment
- It calls fallible tools, APIs, or networks
- Operational reliability is a key requirement
- Graceful degradation or controlled failure is needed

## Don't reach for this when
- A prototype/demo where failure is acceptable
- A failure better surfaced to a human immediately rather than auto-handled

## Shape of the solution
Detect failures proactively (validate outputs, check API error codes, set timeouts). Handle them with logging, retries on transient errors, fallbacks, and graceful degradation. For severe cases, recover by reverting to a stable state, self-correcting the plan, or escalating to a human. Often pairs with reflection for retry-after-critique.

## Common failure modes
- Silent failures
- Infinite retries
- Swallowing errors with no escalation path
- No diagnostics/logging to learn from

## Composes with
- `agentic-tool-use` — the main source of failures
- `agentic-reflection` — self-correct before retrying
- `agentic-human-in-the-loop` — escalation target
- `agentic-evaluation-monitoring` — detect failures and drift

---
*Selection signals live in this skill's `description` (used for auto-triggering). To choose among all 21 patterns, see `agentic-pattern-selector`. Conceptual source: Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems*, Ch. 12 — original distillation from the text, not reproduced prose, code, or figures.*
