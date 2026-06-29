---
name: agentic-pattern-selector
description: Helps choose which agentic design pattern fits a given problem when designing, building, or refactoring an agent or LLM workflow. Use when deciding how to structure an agentic feature, when unsure which pattern applies, or when an existing agent approach is unreliable and you need to diagnose which pattern would fix it. Indexes all 21 patterns from Gulli's Agentic Design Patterns.
---

# Agentic Pattern Selector

Diagnostic index for choosing among the 21 agentic design patterns in Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems*. Start from the problem you're facing; each line points to the pattern skill that addresses it.

## How to use this
1. Find the symptom that best matches your situation below.
2. Open the linked pattern skill for the full when / when-not / shape / failure-modes detail.
3. Patterns compose — most real systems combine several (e.g., planning + tool use + reflection + evaluation).

## Symptom -> pattern

### Structuring the work
- Task splits into a fixed sequence of steps -> `agentic-prompt-chaining`
- Independent subtasks that can run at once -> `agentic-parallelization`
- Different inputs need different handling or models -> `agentic-routing`
- Multi-step goal with an unknown or branching path -> `agentic-planning`
- Ranking competing tasks under constraints -> `agentic-prioritization`
- Open-ended problem, unknown solution space -> `agentic-exploration-discovery`

### Making the agent capable
- Needs live data, computation, or side effects -> `agentic-tool-use`
- Portable, reusable, discoverable tool/data integration -> `agentic-mcp`
- Must ground answers in a corpus or private docs -> `agentic-knowledge-retrieval`
- Complex reasoning, math, or reason+act loops -> `agentic-reasoning-techniques`

### Quality and reliability
- Inconsistent first-pass output, correctness checkable -> `agentic-reflection`
- Failures from fallible tools/APIs need recovery -> `agentic-exception-handling`
- Untrusted input, side effects, policy or safety needs -> `agentic-guardrails-safety`
- Need to know whether it actually works / catch regressions -> `agentic-evaluation-monitoring`
- High-stakes, irreversible, or ambiguous decisions -> `agentic-human-in-the-loop`

### State, scale, autonomy
- Continuity across turns/sessions, recall -> `agentic-memory-management`
- Should improve from feedback over time -> `agentic-learning-adaptation`
- Cost/latency control at scale -> `agentic-resource-aware-optimization`
- Long-running autonomy: track progress and completion -> `agentic-goal-setting-monitoring`

### Multiple agents
- Distinct roles or expertise collaborating -> `agentic-multi-agent`
- Interoperable messaging between agents or systems -> `agentic-inter-agent-communication`

## Decision heuristics
- Don't add a pattern unless a single straightforward call fails. Each pattern buys capability at the cost of latency, money, and failure surface.
- Get it correct with the simplest structure first, then add `agentic-evaluation-monitoring` before optimizing anything.
- "Works in the demo, fails in production" is almost always an evaluation + exception-handling + guardrails gap, not a model problem.
- Reach for `agentic-multi-agent` last, not first: try tool use + planning + reflection inside one agent before splitting into many.
- MCP vs. A2A: MCP connects one agent to tools/data; A2A coordinates multiple agents. Use direct tool-calling before MCP for a small fixed tool set.

## The 21 patterns
| Ch. | Pattern | Skill |
|----|---------|-------|
| 1 | Prompt Chaining | `agentic-prompt-chaining` |
| 2 | Routing | `agentic-routing` |
| 3 | Parallelization | `agentic-parallelization` |
| 4 | Reflection | `agentic-reflection` |
| 5 | Tool Use (Function Calling) | `agentic-tool-use` |
| 6 | Planning | `agentic-planning` |
| 7 | Multi-Agent Collaboration | `agentic-multi-agent` |
| 8 | Memory Management | `agentic-memory-management` |
| 9 | Learning and Adaptation | `agentic-learning-adaptation` |
| 10 | Model Context Protocol (MCP) | `agentic-mcp` |
| 11 | Goal Setting and Monitoring | `agentic-goal-setting-monitoring` |
| 12 | Exception Handling and Recovery | `agentic-exception-handling` |
| 13 | Human-in-the-Loop (HITL) | `agentic-human-in-the-loop` |
| 14 | Knowledge Retrieval (RAG) | `agentic-knowledge-retrieval` |
| 15 | Inter-Agent Communication (A2A) | `agentic-inter-agent-communication` |
| 16 | Resource-Aware Optimization | `agentic-resource-aware-optimization` |
| 17 | Reasoning Techniques | `agentic-reasoning-techniques` |
| 18 | Guardrails / Safety Patterns | `agentic-guardrails-safety` |
| 19 | Evaluation and Monitoring | `agentic-evaluation-monitoring` |
| 20 | Prioritization | `agentic-prioritization` |
| 21 | Exploration and Discovery | `agentic-exploration-discovery` |

---
*Conceptual source: Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems* (2025), 21 patterns across 4 parts. The book's code examples use LangChain/LangGraph, CrewAI, and Google ADK; these skills are framework-agnostic. They are an original distillation built for selection and auto-triggering — not a reproduction of the book's prose, code, or figures. Free to read: https://docs.google.com/document/d/1rsaK53T3Lg5KoGwvf8ukOUvbELRtH-V0LnOIFDxBryE/*
