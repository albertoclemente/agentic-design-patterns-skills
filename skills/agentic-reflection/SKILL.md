---
name: agentic-reflection
description: A feedback loop where the agent evaluates its own output against criteria and revises it — self-correction. Often implemented as a Producer-Critic split, where a separate agent or prompted role critiques the first agent's work for objectivity. Use when output quality must be high, correctness is checkable, or a first pass tends to be incomplete or inaccurate.
---

# Reflection

> Agentic Design Pattern 4 of 21 — distilled from Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems* (Ch. 4).

**What it is.** Run a loop of execution -> evaluation/critique -> refinement. The agent (or a dedicated critic) checks the output against explicit criteria and produces an improved version, iterating up to a cap.

## Reach for this when
- First-pass quality is inconsistent and the result is high-stakes
- Correctness is checkable (tests pass, constraints satisfied, facts verifiable)
- The task needs nuanced or precise output worth an extra pass
- You can express concrete evaluation criteria

## Don't reach for this when
- There's no way to judge better vs. worse
- Latency/cost-sensitive and the first pass is good enough
- You can't define a stopping condition (loops risk runaway cost and context overflow)

## Shape of the solution
Generate, then critique against explicit criteria, then revise. Prefer a Producer-Critic separation (a distinct critic agent/role) for objectivity, and ground the critique in an external signal — test results, tool output, rules — rather than the model grading itself. Cap iterations.

## Common failure modes
- Unbounded loops with no stopping rule
- Self-congratulatory critique with no real signal
- Increased latency, compute, and context-window/throttling risk

## Composes with
- `agentic-tool-use` — tests/tools as the critic signal
- `agentic-exception-handling` — reflect-then-recover on failures
- `agentic-planning` — reflect to replan
- `agentic-evaluation-monitoring` — supplies the criteria

---
*Selection signals live in this skill's `description` (used for auto-triggering). To choose among all 21 patterns, see `agentic-pattern-selector`. Conceptual source: Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems*, Ch. 4 — original distillation from the text, not reproduced prose, code, or figures.*
