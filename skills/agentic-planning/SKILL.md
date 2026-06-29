---
name: agentic-planning
description: The agent takes a high-level goal and autonomously generates a sequence of steps to reach it — defining the 'how' from the 'what'. The plan is created in response to the request (not known in advance) and is adaptable: the agent re-plans around obstacles. Use for complex, multi-step, interdependent tasks; avoid dynamic planning when the path is fixed and known.
---

# Planning

> Agentic Design Pattern 6 of 21 — distilled from Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems* (Ch. 6).

**What it is.** Given a goal and constraints, generate an inspectable plan of interdependent steps, execute them (often via tool use), and re-plan when new information or failure arrives. Separate the planner from the executor.

## Reach for this when
- A request is too complex for a single action or tool
- The path isn't known up front and must be discovered
- Steps have dependencies that need logical ordering
- The task benefits from foresight and adaptation (re-planning around obstacles)

## Don't reach for this when
- The task is a single step or a fixed, known pipeline -> prefer agentic-prompt-chaining (dynamic planning trades predictability for flexibility)
- Plans can't be verified and just drift
- You'd be over-planning a trivial request

## Shape of the solution
Have the agent decompose the goal into actionable sub-steps, execute them, and re-plan when an obstacle appears (e.g., a venue is unavailable -> propose alternatives). Keep the plan explicit and inspectable, and separate planning from execution so deviations are visible.

## Common failure modes
- Brittle plans with no re-planning
- Over-decomposition of simple goals
- Plan and execution drifting apart
- Choosing dynamic planning where a fixed workflow is more predictable

## Composes with
- `agentic-tool-use` — execute plan steps
- `agentic-reflection` — trigger re-planning
- `agentic-goal-setting-monitoring` — track progress to the goal
- `agentic-multi-agent` — delegate plan steps to specialists

---
*Selection signals live in this skill's `description` (used for auto-triggering). To choose among all 21 patterns, see `agentic-pattern-selector`. Conceptual source: Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems*, Ch. 6 — original distillation from the text, not reproduced prose, code, or figures.*
