---
name: agentic-goal-setting-monitoring
description: Gives an agent explicit objectives plus a mechanism to track progress and judge success, creating a feedback loop that lets it correct course or adapt its plan. Goals should be SMART (specific, measurable, achievable, relevant, time-bound). Use when an agent must autonomously run a multi-step task, adapt to changing conditions, and reliably reach a high-level objective without constant supervision.
---

# Goal Setting and Monitoring

> Agentic Design Pattern 11 of 21 — distilled from Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems* (Ch. 11).

**What it is.** Define clear, measurable goals and success criteria, then continuously monitor the agent's actions, environment state, and tool outputs against them — feeding deviations back into adaptation, re-planning, or escalation.

## Reach for this when
- An agent must autonomously execute a multi-step task to a defined objective
- You need to know whether it's on track and when it's done
- Objectives can be made measurable (SMART)
- You're preventing aimless, non-terminating behavior

## Don't reach for this when
- Trivial single-step tasks with obvious completion
- Goals that genuinely can't be specified or measured

## Shape of the solution
State the goal, define metrics and success criteria up front, and monitor actions/environment/tool outputs against them. Use the resulting feedback loop to let the agent self-assess, revise its plan, or escalate when it deviates from the path to success.

## Common failure modes
- Vague, unmeasurable goals
- No termination condition
- Gaming the success metric
- No genuine progress checks

## Composes with
- `agentic-planning` — produces the steps toward the goal
- `agentic-evaluation-monitoring` — the measurement machinery
- `agentic-exception-handling` — handle deviations
- `agentic-human-in-the-loop` — escalate when stuck

---
*Selection signals live in this skill's `description` (used for auto-triggering). To choose among all 21 patterns, see `agentic-pattern-selector`. Conceptual source: Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems*, Ch. 11 — original distillation from the text, not reproduced prose, code, or figures.*
