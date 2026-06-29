---
name: agentic-memory-management
description: Gives an agent short-term memory (recent context within the LLM window) and long-term memory (persistent knowledge in external storage, usually a vector DB retrieved semantically). Use when an agent must maintain conversational context, track progress across multi-step tasks, personalize from user history, or learn from past interactions — anything beyond a single stateless exchange.
---

# Memory Management

> Agentic Design Pattern 8 of 21 — distilled from Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems* (Ch. 8).

**What it is.** Run a dual memory system: short-term contextual memory (windowing or summarizing recent turns) plus long-term memory (an external/vector store written to and retrieved semantically), deciding what to persist, retrieve, and forget.

## Reach for this when
- The agent must maintain context across a conversation
- It must track progress through a multi-step task
- Personalization from user preferences/history is needed
- It should recall facts or experiences across sessions

## Don't reach for this when
- Stateless, single-shot tasks
- Memory adds complexity with no real recall need
- You'd be persisting everything indiscriminately

## Shape of the solution
For short-term memory, keep the most relevant content in the context window (summarize older segments rather than dumping everything). For long-term memory, write durable facts to an external store and retrieve them semantically when relevant. Define explicit policies for what to persist, retrieve, and forget.

## Common failure modes
- Context bloat from carrying too much forward
- Stale or contradictory stored memories
- Retrieval noise surfacing irrelevant facts
- Privacy of persisted data

## Composes with
- `agentic-knowledge-retrieval` — retrieval mechanics for long-term memory
- `agentic-learning-adaptation` — learn from stored experience
- `agentic-multi-agent` — shared memory across agents

---
*Selection signals live in this skill's `description` (used for auto-triggering). To choose among all 21 patterns, see `agentic-pattern-selector`. Conceptual source: Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems*, Ch. 8 — original distillation from the text, not reproduced prose, code, or figures.*
