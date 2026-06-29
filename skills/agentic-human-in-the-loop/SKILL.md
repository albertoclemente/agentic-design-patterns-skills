---
name: agentic-human-in-the-loop
description: Deliberately interweaves human judgment with agent autonomy via oversight, intervention, feedback for learning, and decision augmentation, with clear escalation policies. Use for complex, ambiguous, or high-stakes/high-risk decisions where full autonomy is imprudent. Note the core trade-off: HITL improves safety and accuracy but doesn't scale and depends on skilled experts.
---

# Human-in-the-Loop (HITL)

> Agentic Design Pattern 13 of 21 — distilled from Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems* (Ch. 13).

**What it is.** Insert human checkpoints — approval, intervention, or feedback — at high-risk or low-confidence decisions, with explicit escalation policies for when the agent should hand off to a person.

## Reach for this when
- High-stakes, high-risk, or irreversible actions
- Ambiguous or complex decisions where errors are costly
- Safety, ethics, or compliance require human oversight
- You're building trust during rollout, or confidence is low

## Don't reach for this when
- High-volume, low-stakes tasks where review is the bottleneck (accuracy/volume trade-off)
- Latency-critical automation
- Cases where a human adds no real signal

## Shape of the solution
Define approval gates and escalation policies, surface confidence and enough context for a fast, informed human decision, and capture those decisions (they also become training data). Choose blocking vs. asynchronous review by risk level; anonymize sensitive data shown to reviewers.

## Common failure modes
- Review fatigue and rubber-stamping
- Throughput bottlenecks (HITL doesn't scale)
- Unclear escalation criteria
- Privacy exposure of data shown to humans

## Composes with
- `agentic-exception-handling` — escalate failures here
- `agentic-guardrails-safety` — gate risky actions
- `agentic-goal-setting-monitoring` — checkpoint progress
- `agentic-learning-adaptation` — learn from human decisions

---
*Selection signals live in this skill's `description` (used for auto-triggering). To choose among all 21 patterns, see `agentic-pattern-selector`. Conceptual source: Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems*, Ch. 13 — original distillation from the text, not reproduced prose, code, or figures.*
