---
name: agentic-routing
description: Classifies an incoming request and dynamically directs control to the most appropriate tool, function, sub-agent, or workflow. Use when an agent must triage diverse inputs and pick among multiple distinct handlers based on intent or state — e.g., a support bot splitting sales, technical, and account queries. Routing can be driven by an LLM classifier, rules, or embedding similarity.
---

# Routing

> Agentic Design Pattern 2 of 21 — distilled from Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems* (Ch. 2).

**What it is.** Analyze the input to determine intent or type, then route the flow of control to the best-fit handler, tool, model, or sub-agent — turning a fixed path into a context-aware decision.

## Reach for this when
- Inputs are varied and need different handling
- An agent must triage or classify requests before acting
- Multiple specialized tools or sub-agents exist and exactly one should run
- You want to send simple queries to cheap models and hard ones to strong models

## Don't reach for this when
- Every input legitimately follows the same path
- Only one handler exists
- The routing decision is itself as costly or error-prone as just doing the work

## Shape of the solution
Implement the classifier with an LLM prompt, rule set, or embedding-similarity match. Define an exhaustive set of categories plus an explicit default/fallback, and keep the router's job narrow so accuracy holds as categories grow.

## Common failure modes
- Silent mis-routes with no fallback path
- A missing default category
- Router accuracy drifting as categories proliferate

## Composes with
- `agentic-prompt-chaining` — route into a specific chain
- `agentic-multi-agent` — route to a specialist agent
- `agentic-resource-aware-optimization` — route by cost/complexity
- `agentic-tool-use` — route to the right tool

---
*Selection signals live in this skill's `description` (used for auto-triggering). To choose among all 21 patterns, see `agentic-pattern-selector`. Conceptual source: Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems*, Ch. 2 — original distillation from the text, not reproduced prose, code, or figures.*
