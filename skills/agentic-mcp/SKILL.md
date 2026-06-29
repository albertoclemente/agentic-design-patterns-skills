---
name: agentic-mcp
description: An open standard that acts as a universal adapter between LLMs and external systems, exposing data (resources), templates (prompts), and functions (tools) over a client-server protocol with dynamic discovery. Use for complex, scalable, or enterprise systems that must interoperate with a diverse, evolving set of tools and data; for a small fixed set of functions, direct tool-calling is simpler.
---

# Model Context Protocol (MCP)

> Agentic Design Pattern 10 of 21 — distilled from Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems* (Ch. 10).

**What it is.** Expose or consume capabilities — tools, data resources, and prompts — over the MCP client-server protocol so integrations are standardized, reusable, and discoverable, instead of bespoke per-tool glue.

## Reach for this when
- Building complex, scalable, or enterprise-grade agentic systems
- Integrating a diverse and evolving set of external tools/data sources
- Interoperability across different LLMs and tools is a priority
- Agents need to discover new capabilities dynamically without redeployment

## Don't reach for this when
- A simple app with a small, fixed set of predefined functions -> direct tool-calling (agentic-tool-use) is sufficient
- No reuse of tools across agents/clients
- The integration is trivial and the protocol overhead isn't justified

## Shape of the solution
Run or consume MCP servers that expose resources, prompts, and tools via the standard client-server contract with dynamic discovery. Treat MCP as the reusable transport layer beneath the tool-use pattern; its value is interoperability and avoiding custom integrations.

## Common failure modes
- Over-engineering simple integrations
- Server reliability and security
- Version drift across servers and clients

## Composes with
- `agentic-tool-use` — what MCP standardizes and delivers
- `agentic-inter-agent-communication` — A2A coordinates agents; MCP connects an agent to resources
- `agentic-guardrails-safety` — vet third-party servers

---
*Selection signals live in this skill's `description` (used for auto-triggering). To choose among all 21 patterns, see `agentic-pattern-selector`. Conceptual source: Antonio Gulli, *Agentic Design Patterns: A Hands-On Guide to Building Intelligent Systems*, Ch. 10 — original distillation from the text, not reproduced prose, code, or figures.*
