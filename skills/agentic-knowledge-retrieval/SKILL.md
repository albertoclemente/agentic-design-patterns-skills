---
name: agentic-knowledge-retrieval
description: Grounds an LLM in external knowledge: retrieve relevant snippets from a knowledge base, augment the prompt with them, then generate — yielding accurate, up-to-date, attributable answers. Use when responses must be grounded in current, private, or specialized data the model wasn't trained on, to reduce hallucination, or to cite sources. Variants include GraphRAG and Agentic RAG.
---

# Knowledge Retrieval (RAG)

> Agentic Design Pattern 14 of 21 — distilled from Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems* (Ch. 14).

**What it is.** Retrieve relevant passages from an indexed knowledge base, augment the prompt with them, and generate a grounded, citable answer — so the model 'looks things up' instead of relying only on training data.

## Reach for this when
- Answers must be grounded in current, private, or specialized data
- You need to reduce hallucination or provide attributable, cited answers
- Knowledge changes faster than the model's training
- The corpus is too large to fit directly in context

## Don't reach for this when
- The model already knows it reliably
- The corpus is small enough to place directly in context
- Retrieval quality is poor and unmanaged (garbage in, garbage out)

## Shape of the solution
Chunk, embed, and index the corpus; on a query, retrieve relevant snippets (rerank as needed), augment the prompt, and generate with citations. Consider GraphRAG when answers require synthesizing across related facts, and Agentic RAG when the agent should reason about, validate, and refine what it retrieves. Evaluate retrieval separately from generation.

## Common failure modes
- Poor chunking or retrieval
- A stale index
- Lost-in-the-middle context
- Ungrounded synthesis despite retrieval
- No retrieval evaluation

## Composes with
- `agentic-memory-management` — the long-term store
- `agentic-tool-use` — retrieval exposed as a tool
- `agentic-reflection` — verify grounding (Agentic RAG)
- `agentic-evaluation-monitoring` — retrieval metrics

---
*Selection signals live in this skill's `description` (used for auto-triggering). To choose among all 21 patterns, see `agentic-pattern-selector`. Conceptual source: Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems*, Ch. 14 — original distillation from the text, not reproduced prose, code, or figures.*
