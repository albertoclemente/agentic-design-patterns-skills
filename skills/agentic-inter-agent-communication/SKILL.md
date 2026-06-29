---
name: agentic-inter-agent-communication
description: An open, HTTP-based standard for agents built on different frameworks to coordinate, delegate tasks, and share information. A core piece is the Agent Card — a digital identity describing an agent's capabilities and endpoints for discovery. Supports synchronous, asynchronous, and streaming interactions with built-in security (mTLS, auth). Use to orchestrate collaboration across heterogeneous agents.
---

# Inter-Agent Communication (A2A)

> Agentic Design Pattern 15 of 21 — distilled from Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems* (Ch. 15).

**What it is.** Let distinct agents interoperate over the A2A protocol: publish capabilities via Agent Cards for discovery, then coordinate, delegate, and exchange results across frameworks using sync, async, or streaming interactions.

## Reach for this when
- Two or more agents must collaborate, especially across different frameworks (ADK, LangGraph, CrewAI)
- You're building modular apps where specialized agents own parts of a workflow
- An agent needs to dynamically discover and use other agents' capabilities
- Interoperability across vendors/platforms matters

## Don't reach for this when
- A single agent does the work
- Tightly-coupled, in-process calls suffice
- The protocol overhead isn't justified for the scope

## Shape of the solution
Describe each agent with an Agent Card (capabilities, skills, endpoints) for discovery, choose interaction modes (synchronous request/response, async polling, or streaming), and secure communication (mTLS, explicit auth). A2A handles high-level task coordination between agents; MCP connects an individual agent to its resources.

## Common failure modes
- Protocol or schema mismatch
- Message loops
- Lost messages
- No timeout/error semantics

## Composes with
- `agentic-multi-agent` — the collaboration layer A2A serves
- `agentic-mcp` — complementary: MCP for agent-to-resource, A2A for agent-to-agent
- `agentic-exception-handling` — message failures

---
*Selection signals live in this skill's `description` (used for auto-triggering). To choose among all 21 patterns, see `agentic-pattern-selector`. Conceptual source: Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems*, Ch. 15 — original distillation from the text, not reproduced prose, code, or figures.*
