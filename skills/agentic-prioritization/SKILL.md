---
name: agentic-prioritization
description: Lets an agent rank and sequence competing tasks, goals, and actions using explicit criteria — urgency, importance, dependencies, resource availability, cost/benefit, and user preferences — at both strategic and tactical levels, with dynamic re-prioritization as conditions change. Use when an agent must autonomously manage multiple, often conflicting, tasks under resource constraints.
---

# Prioritization

> Agentic Design Pattern 20 of 21 — distilled from Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems* (Ch. 20).

**What it is.** Score and rank competing tasks against explicit criteria, act on the highest-priority ones first, and dynamically re-prioritize as circumstances change.

## Reach for this when
- An agent faces many possible actions or conflicting goals
- Resources, time, or budget are constrained
- It must autonomously decide what to do next
- Queues, scheduling, or triage are involved

## Don't reach for this when
- A single task
- A fixed, known order of operations
- A trivial backlog where ranking adds no value

## Shape of the solution
Define criteria (urgency, importance, dependencies, resource availability, cost/benefit, user preferences) and evaluate each candidate task against them with rules or LLM reasoning. Prioritize at both strategic (goals) and tactical (immediate actions) levels, and re-prioritize dynamically as conditions shift — while preventing starvation of low-priority work.

## Common failure modes
- Starvation of low-priority tasks
- Thrashing from over-frequent re-ranking
- Ignoring dependencies
- Static priorities that never update

## Composes with
- `agentic-planning` — sequence the chosen work
- `agentic-goal-setting-monitoring` — align priorities to goals
- `agentic-resource-aware-optimization` — weigh resource cost
- `agentic-multi-agent` — allocate across agents

---
*Selection signals live in this skill's `description` (used for auto-triggering). To choose among all 21 patterns, see `agentic-pattern-selector`. Conceptual source: Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems*, Ch. 20 — original distillation from the text, not reproduced prose, code, or figures.*
