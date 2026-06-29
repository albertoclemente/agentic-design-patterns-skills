---
name: agentic-guardrails-safety
description: A multi-layered defense that keeps agents safe, ethical, and on-task as autonomy grows: input validation/sanitization, output filtering/post-processing, prompt-level behavioral constraints, tool-use restrictions, external moderation APIs, and human oversight. Defends against harmful/biased output and adversarial attacks like jailbreaking. Use for any agent with untrusted input, real side effects, or compliance needs.
---

# Guardrails / Safety Patterns

> Agentic Design Pattern 18 of 21 — distilled from Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems* (Ch. 18).

**What it is.** Wrap the agent in layered controls — validate inputs, filter outputs, constrain behavior via prompts, restrict tool permissions, call moderation APIs, and add human oversight — so it operates safely and predictably even under adversarial input.

## Reach for this when
- Input is untrusted or adversarial (jailbreak risk)
- The agent has real side effects or elevated permissions
- Compliance, safety, brand, or legal constraints apply
- You must prevent harmful, biased, or off-topic output

## Don't reach for this when
- A closed sandbox prototype with no real users may need only a light touch — but production with real users always warrants guardrails

## Shape of the solution
Layer the defenses: sanitize and validate inputs, filter/post-process outputs for toxicity or policy violations, set prompt-level behavioral constraints, restrict which tools the agent may call, use external moderation APIs, and keep humans in the loop for risky actions. A small, cheap model can act as a fast pre-screen for inputs and outputs. Fail closed on high risk.

## Common failure modes
- Guardrails too loose (bypassed) or too tight (false refusals)
- Missing defenses against prompt injection/jailbreaks
- Over-permissioned tools

## Composes with
- `agentic-tool-use` — restrict tool capabilities
- `agentic-human-in-the-loop` — oversight for risky actions
- `agentic-exception-handling` — fail closed safely
- `agentic-evaluation-monitoring` — detect violations

---
*Selection signals live in this skill's `description` (used for auto-triggering). To choose among all 21 patterns, see `agentic-pattern-selector`. Conceptual source: Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems*, Ch. 18 — original distillation from the text, not reproduced prose, code, or figures.*
