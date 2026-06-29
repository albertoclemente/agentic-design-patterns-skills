---
name: agentic-multi-agent
description: Structures a system as a cooperative ensemble of specialized agents, each with the tools and skills for its sub-problem, coordinating via a shared protocol. Collaboration models include sequential handoffs, parallel workstreams, hierarchical delegation, and debate. Use when a task is too complex for one agent and decomposes into sub-tasks needing diverse expertise; try a single agent first.
---

# Multi-Agent Collaboration

> Agentic Design Pattern 7 of 21 — distilled from Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems* (Ch. 7).

**What it is.** Decompose a high-level objective into sub-problems, assign each to a specialized agent, and coordinate them through defined communication and an interaction model (handoffs, parallel, hierarchical, or debate).

## Reach for this when
- A task is too complex for one agent and splits into distinct sub-tasks
- Sub-tasks need diverse, specialized skills or tools
- The work benefits from parallel specialized effort or multi-stage structure
- Debate/critique between agents would improve quality

## Don't reach for this when
- A single agent handles it fine (multi-agent adds coordination cost and failure surface)
- Cost/latency-sensitive workloads
- Coordination overhead would outweigh the benefit

## Shape of the solution
Define roles and responsibilities, pick a topology (sequential handoff, parallel, hierarchical/supervisor, or debate), and specify the communication protocol, shared context, and termination condition. Efficacy depends as much on coordination as on the division of labor.

## Common failure modes
- Coordination overhead and message loops
- Diffused responsibility
- Cost and latency multiply
- Emergent miscommunication between agents

## Composes with
- `agentic-inter-agent-communication` — the messaging/coordination layer
- `agentic-routing` — dispatch to a specialist
- `agentic-planning` — decompose and delegate
- `agentic-memory-management` — shared state

---
*Selection signals live in this skill's `description` (used for auto-triggering). To choose among all 21 patterns, see `agentic-pattern-selector`. Conceptual source: Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems*, Ch. 7 — original distillation from the text, not reproduced prose, code, or figures.*
