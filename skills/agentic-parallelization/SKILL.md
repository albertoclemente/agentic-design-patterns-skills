---
name: agentic-parallelization
description: Executes independent sub-tasks concurrently instead of sequentially, then aggregates results. Use when a workflow has multiple operations that don't depend on each other's output — especially I/O-bound work like calling several APIs or querying multiple sources — so total time is the longest task, not the sum of all of them.
---

# Parallelization

> Agentic Design Pattern 3 of 21 — distilled from Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems* (Ch. 3).

**What it is.** Identify components that don't rely on each other's immediate output, run them concurrently, and wait for all before aggregating (reduce, merge, or vote).

## Reach for this when
- A workflow has multiple genuinely independent operations
- Tasks are I/O-bound (multiple API calls, database queries, document fetches)
- You're generating several pieces in parallel for later synthesis
- Ensembling or majority-voting across generations improves quality

## Don't reach for this when
- Steps depend on each other's outputs -> use agentic-prompt-chaining
- Rate limits or cost make wide fan-out impractical
- The aggregation/synthesis logic is the hard part and isn't well defined

## Shape of the solution
Fan out the independent calls concurrently, gather results, and reduce. Handle partial failures and per-call timeouts so one slow or failed call doesn't gate the batch. Note that concurrency adds real complexity to design, debugging, and logging — adopt it only where the latency win is worth it.

## Common failure modes
- Weak aggregation undermines the parallel work
- Cost spikes from wide fan-out
- Harder debugging and logging under concurrency
- One slow call stalling the whole batch

## Composes with
- `agentic-reflection` — critique or vote across candidates
- `agentic-prompt-chaining` — a parallel stage inside a chain
- `agentic-resource-aware-optimization` — bound fan-out cost

---
*Selection signals live in this skill's `description` (used for auto-triggering). To choose among all 21 patterns, see `agentic-pattern-selector`. Conceptual source: Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems*, Ch. 3 — original distillation from the text, not reproduced prose, code, or figures.*
