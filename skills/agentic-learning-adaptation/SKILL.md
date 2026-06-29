---
name: agentic-learning-adaptation
description: The agent changes its behavior, knowledge, or strategy based on new experience and data — adaptation is the visible result of learning. Mechanisms span reinforcement, supervised, unsupervised, and few-/zero-shot learning, up to self-modifying systems. Use for agents in dynamic, uncertain, or evolving environments that need personalization, continuous improvement, or to handle novel situations autonomously.
---

# Learning and Adaptation

> Agentic Design Pattern 9 of 21 — distilled from Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems* (Ch. 9).

**What it is.** Close a loop: capture outcomes and feedback, then update the agent's behavior — via few-shot examples, prompt/strategy changes, policies, or (for advanced systems) self-modification — so it improves over time.

## Reach for this when
- The agent operates in a dynamic, uncertain, or evolving environment
- Pre-programmed logic degrades on situations not anticipated at design time
- Personalization or continuous performance improvement is the goal
- Reliable feedback signals are available to learn from

## Don't reach for this when
- One-off tasks with no repeat value
- No trustworthy feedback signal exists
- The learning loop costs more than it returns
- Outcomes can't be measured

## Shape of the solution
Capture outcomes and feedback, then update the appropriate lever — for API-consumer apps that usually means evolving few-shot examples, prompts, or routing/selection policies rather than weights. Evaluation is the substrate that confirms whether a change actually helped, and guards against drift.

## Common failure modes
- Reward hacking and gaming the signal
- Drift over time
- Learning from noisy or biased feedback
- No rollback when a change regresses quality

## Composes with
- `agentic-memory-management` — store the experience to learn from
- `agentic-evaluation-monitoring` — verify learning helps
- `agentic-reflection` — in-loop self-correction
- `agentic-exploration-discovery` — gather new experience

---
*Selection signals live in this skill's `description` (used for auto-triggering). To choose among all 21 patterns, see `agentic-pattern-selector`. Conceptual source: Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems*, Ch. 9 — original distillation from the text, not reproduced prose, code, or figures.*
