---
name: agentic-tool-use
description: Lets the LLM call external functions, APIs, databases, or code to fetch real data and take action. The model decides when a tool is needed and emits a structured call (e.g., JSON) that an orchestration layer executes, feeding the result back. Use whenever the agent must break out of static internal knowledge — real-time data, private/proprietary data, precise calculation, code execution, or triggering actions.
---

# Tool Use (Function Calling)

> Agentic Design Pattern 5 of 21 — distilled from Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems* (Ch. 5).

**What it is.** Describe available tools (name, purpose, typed parameters) to the LLM; it decides when to call one and emits a structured function call; an orchestration layer runs it and returns the result for the model to use.

## Reach for this when
- The task needs real-time or external data
- Access to private/proprietary systems (a company database, internal API)
- Precise computation or code execution is required
- The agent must take actions in other systems (send email, update a record)

## Don't reach for this when
- The model already answers reliably from internal knowledge
- The tool set is so large it degrades selection — curate it
- A single deterministic call would do without an agent wrapper

## Shape of the solution
Define each tool with a crisp description and typed parameters, keep the set small and unambiguous, validate generated arguments, execute via the orchestration layer, handle tool errors, and feed results back. Constrain permissions tightly for any tool with side effects.

## Common failure modes
- Hallucinated or malformed arguments
- Too many tools degrade selection accuracy
- Unhandled tool failures
- Over-permissioned destructive tools

## Composes with
- `agentic-mcp` — standardized transport for tools
- `agentic-reasoning-techniques` — reason+act (ReAct) loops
- `agentic-guardrails-safety` — restrict tool capabilities
- `agentic-exception-handling` — recover from tool errors

---
*Selection signals live in this skill's `description` (used for auto-triggering). To choose among all 21 patterns, see `agentic-pattern-selector`. Conceptual source: Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems*, Ch. 5 — original distillation from the text, not reproduced prose, code, or figures.*
