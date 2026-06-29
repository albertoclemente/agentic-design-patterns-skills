# Contributing

Contributions are welcome — corrections, sharper `description` triggers, better failure-mode notes, or additional "composes with" links.

## Guidelines
- **Keep each `SKILL.md` lean.** Claude reads the body into context when the skill triggers; every token competes with the rest of the conversation.
- **The `description` is the product.** It drives auto-triggering. Write it in third person, state what the pattern does *and* when to use it, and include concrete symptom phrases.
- **Don't reproduce the book.** Patterns and their names are fair to reference; the book's prose, code, and figures are not. Keep contributions as original distillations.
- **Test triggering.** Install the skill, describe a matching problem in a fresh session, and confirm the right skill surfaces.
- One pattern per skill. Cross-link related patterns rather than merging them.

## Structure
```
skills/<skill-name>/SKILL.md   # folder name must match the frontmatter `name`
```
`name`: lowercase letters, numbers, hyphens only (max 64 chars). `description`: max 1024 chars.
