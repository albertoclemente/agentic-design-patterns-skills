---
name: agentic-resource-aware-optimization
description: Lets an agent dynamically monitor and manage compute, time, and money during operation — trading output quality against cost. A common design uses a Router Agent to classify request complexity (cheap model for simple, strong model for complex), a Critique Agent to refine routing, and fallback mechanisms for graceful degradation. Use under budget, latency, or hardware constraints.
---

# Resource-Aware Optimization

> Agentic Design Pattern 16 of 21 — distilled from Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems* (Ch. 16).

**What it is.** Tier work to the cheapest sufficient resource: classify request complexity and route to a fast/cheap or powerful/expensive model accordingly, prune or summarize context, enforce budgets, and fall back gracefully when a model is throttled or unavailable.

## Reach for this when
- Operating under financial budgets for API/compute
- Latency-sensitive applications needing fast responses
- Deploying on resource-constrained hardware (edge, limited battery)
- Balancing response quality against operational cost across varied task complexity

## Don't reach for this when
- Prototype or low-volume usage
- Optimizing before correctness is established
- The savings are negligible relative to the added complexity

## Shape of the solution
Use a Router Agent to classify incoming complexity and direct simple queries to a fast cheap model and hard ones to a powerful model; add a Critique Agent to evaluate quality and improve routing over time. Apply contextual pruning/summarization, set budgets, and define fallback to a default model for graceful degradation under throttling.

## Common failure modes
- Premature optimization before it works
- Cache or routing staleness
- Quality regressions from cheaper models
- No visibility into cost per task

## Composes with
- `agentic-routing` — the complexity-based router at its core
- `agentic-evaluation-monitoring` — guard quality while cutting cost
- `agentic-memory-management` — context pruning/summarization
- `agentic-exception-handling` — fallback on throttling

---
*Selection signals live in this skill's `description` (used for auto-triggering). To choose among all 21 patterns, see `agentic-pattern-selector`. Conceptual source: Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems*, Ch. 16 — original distillation from the text, not reproduced prose, code, or figures.*
