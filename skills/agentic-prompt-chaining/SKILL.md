---
name: agentic-prompt-chaining
description: Decomposes a complex task into a sequence of focused LLM calls (a pipeline) where each step's output becomes the next step's input. Use when a task is too complex or multi-constraint for one prompt, when it has distinct processing stages, when external tools must be invoked between steps, or when a multi-step workflow needs to build up and maintain state. Also called the Pipeline pattern.
---

# Prompt Chaining

> Agentic Design Pattern 1 of 21 — distilled from Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems* (Ch. 1).

**What it is.** Break a complex task into an ordered chain of focused prompts; each step performs one operation and passes its (ideally structured) output to the next, building progressively toward the result.

## Reach for this when
- A task is too complex or has too many constraints for a single reliable prompt
- It has distinct, sequential processing stages (e.g., extract -> transform -> format)
- External tools or structured data must be integrated between steps
- A multi-step workflow needs to carry state forward

## Don't reach for this when
- Steps are independent and could run together -> use agentic-parallelization
- The path varies by input rather than being fixed -> use agentic-routing
- A single focused prompt already produces reliable output (chaining only adds latency, cost, and error-propagation surface)

## Shape of the solution
Define discrete steps, give each a narrow prompt scoped to one operation, and pass structured output forward. Add validation gates between steps so a bad intermediate result is caught early instead of compounding down the chain.

## Common failure modes
- Errors compound as they propagate down the chain
- Latency and token cost stack with each call
- Over-decomposing a task that one prompt handles fine

## Composes with
- `agentic-routing` — choose which chain to run
- `agentic-tool-use` — call external systems between steps
- `agentic-reflection` — verify a step before continuing
- `agentic-evaluation-monitoring` — trace per-step quality

---
*Selection signals live in this skill's `description` (used for auto-triggering). To choose among all 21 patterns, see `agentic-pattern-selector`. Conceptual source: Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems*, Ch. 1 — original distillation from the text, not reproduced prose, code, or figures.*
