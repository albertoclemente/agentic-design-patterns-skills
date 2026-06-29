---
name: agentic-reasoning-techniques
description: Structured methods that make an agent's internal problem-solving explicit and allocate more inference-time 'thinking' to hard problems: Chain-of-Thought (stepwise), Tree-of-Thought (explore/backtrack across strategies), Self-Correction, ReAct (interleave reasoning with tool actions), and Chain-of-Debate (multi-agent). Use when a problem is too complex for a single pass and showing the work matters.
---

# Reasoning Techniques

> Agentic Design Pattern 17 of 21 — distilled from Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems* (Ch. 17).

**What it is.** Apply a structured reasoning method matched to the problem: CoT to break it into steps, ToT/self-correction to deliberate across and backtrack between strategies, and ReAct to interleave reasoning with tool calls in a thought-action-observation loop.

## Reach for this when
- A problem is too complex for a single-pass answer
- It needs decomposition, multi-step logic, or strategic planning
- Reasoning must interleave with external tools/data (ReAct)
- Showing the reasoning ('the work') matters as much as the answer

## Don't reach for this when
- Simple lookups where reasoning just adds cost and latency
- Verbose reasoning doesn't measurably improve accuracy
- The task is better solved directly by tools or retrieval

## Shape of the solution
Match technique to task: CoT for an explicit stepwise plan, Tree-of-Thought and self-correction to evaluate multiple strategies and backtrack, ReAct to establish the thought-action-observation loop with tools, and Chain-of-Debate for multiple agents to reason together. More allocated inference time generally raises quality on hard problems — budget it deliberately.

## Common failure modes
- Rationalized but wrong answers
- Cost blowup from excessive 'thinking'
- Overthinking trivial tasks

## Composes with
- `agentic-tool-use` — the 'act' half of ReAct
- `agentic-reflection` — critique and refine reasoning
- `agentic-planning` — higher-level decomposition
- `agentic-multi-agent` — Chain-of-Debate

---
*Selection signals live in this skill's `description` (used for auto-triggering). To choose among all 21 patterns, see `agentic-pattern-selector`. Conceptual source: Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems*, Ch. 17 — original distillation from the text, not reproduced prose, code, or figures.*
