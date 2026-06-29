---
name: agentic-exploration-discovery
description: Enables agents to proactively seek novel information, experiment with new approaches, and surface 'unknown unknowns' rather than optimize within a known solution space. Often realized with multi-agent setups emulating the scientific method — generate hypotheses, critique them, evolve the best. Use in open-ended, complex, or rapidly evolving domains where the solution space isn't defined.
---

# Exploration and Discovery

> Agentic Design Pattern 21 of 21 — distilled from Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems* (Ch. 21).

**What it is.** Have the agent venture beyond known paths — generating and testing hypotheses, experimenting, and capturing new knowledge — while balancing exploration against exploitation under a budget.

## Reach for this when
- Open-ended problems with an undefined solution space
- Complex or rapidly evolving domains
- Generating novel hypotheses, strategies, or insights (research, market analysis, creative work)
- The goal is to uncover unknown unknowns, not optimize a known process

## Don't reach for this when
- A well-defined task with a known solution -> exploit, don't explore
- Exploration cost is high and the payoff is low
- Deterministic pipelines

## Shape of the solution
Balance explore vs. exploit and bound the exploration budget. A common structure is a multi-agent, scientific-method loop: one role generates hypotheses, another critically reviews them, and the most promising are evolved and tested. Capture what's learned so discoveries feed back into the system.

## Common failure modes
- Aimless wandering with no exploitation of findings
- Unbounded cost
- Failing to capture and reuse what's discovered

## Composes with
- `agentic-learning-adaptation` — absorb discoveries
- `agentic-reasoning-techniques` — structure hypothesis search
- `agentic-multi-agent` — hypothesis/critique/evolve roles
- `agentic-evaluation-monitoring` — score discoveries

---
*Selection signals live in this skill's `description` (used for auto-triggering). To choose among all 21 patterns, see `agentic-pattern-selector`. Conceptual source: Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems*, Ch. 21 — original distillation from the text, not reproduced prose, code, or figures.*
