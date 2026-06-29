---
name: agentic-evaluation-monitoring
description: Continuously assesses agent effectiveness, efficiency, and adherence to requirements — beyond traditional testing, because agents are probabilistic and degrade with drift. Combines metrics (accuracy, latency, token usage), trajectory analysis (comparing the agent's action sequence to a ground-truth path), LLM-as-a-Judge for subjective quality, A/B testing, and unit + integration (evalset) tests. Use for anything you ship and iterate on.
---

# Evaluation and Monitoring

> Agentic Design Pattern 19 of 21 — distilled from Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems* (Ch. 19).

**What it is.** Make quality measurable: define metrics, run offline evals (unit tests and evalsets, including trajectory comparison and LLM-as-a-Judge), and monitor production for latency, cost, drift, and anomalies — feeding findings back into iteration.

## Reach for this when
- Any agent you intend to deploy and iterate on
- You need to know whether a change helps or hurts (A/B testing)
- Regulated or high-stakes domains needing compliance/safety audits
- Performance may degrade over time from data or environment drift

## Don't reach for this when
- A genuine throwaway script (otherwise invest proportional to stakes)

## Shape of the solution
Define metrics for accuracy, latency, and token usage; evaluate not just final answers but the agent's trajectory against a ground-truth path; use LLM-as-a-Judge for subjective qualities like helpfulness. Build unit tests and evalsets (run via UI, CLI, or pytest in CI/CD), monitor production continuously, and alert on drift or anomalies.

## From agents to contractors
The book frames an evolution from probabilistic agents toward more deterministic, accountable **contractors** (Gulli et al., *Agent Companion*) — a model that makes evaluation intrinsic rather than bolted on:
- **Formalized contract** — a detailed spec that is the single source of truth for the deliverable and its acceptance criteria
- **Negotiation & feedback** — the agent flags ambiguities and risks and resolves them *before* execution
- **Quality-focused iterative execution** — it self-validates and refines against the contract's criteria until they pass
- **Hierarchical decomposition** — a primary contractor spawns formal *subcontracts* for complex sub-tasks

Putting acceptance criteria in the contract makes outputs measurable and auditable by construction.

## Common failure modes
- Shipping with no evals
- Vanity metrics that don't track task success
- No production tracing
- Eval/production mismatch

## Composes with
- `agentic-reflection` — supplies and consumes criteria
- `agentic-learning-adaptation` — the improvement loop
- `agentic-resource-aware-optimization` — track cost/latency
- every other pattern — this is the feedback substrate

---
*Selection signals live in this skill's `description` (used for auto-triggering). To choose among all 21 patterns, see `agentic-pattern-selector`. Conceptual source: Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems*, Ch. 19 — original distillation from the text, not reproduced prose, code, or figures.*
