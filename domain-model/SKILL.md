---
name: domain-model
description: >
  Grilling session that challenges your understanding of the domain, sharpens terminology,
  builds a CONTEXT.md glossary, and creates ADRs for hard-to-reverse decisions. Use for
  "what IS this world?" — defining domain concepts, naming things, establishing bounded
  contexts, and building the shared language that all future work depends on. Use when
  starting a new domain, onboarding into unfamiliar territory, or when terms feel fuzzy.
disable-model-invocation: true
---

Interview me relentlessly about every aspect of this plan until we reach a shared understanding. Walk down each branch of the design tree, resolving dependencies between decisions one-by-one. For each question, provide your recommended answer.

Ask the questions one at a time, waiting for feedback on each question before continuing.

If a question can be answered by exploring the codebase, explore the codebase instead.

## What this skill is for

This is the "what IS this world?" skill. Before you build anything, you need to know what things are, what they're called, and how they relate. This skill grills you until the domain is mapped — then persists that map so every future conversation starts from shared ground.

## Domain awareness

**Before creating any files, check the repo's AGENTS.md for domain context conventions.** Some repos specify where CONTEXT.md and ADRs must live. If AGENTS.md defines a convention, follow it instead of the defaults below.

During codebase exploration, also look for existing documentation:

### File structure (defaults — override if AGENTS.md says otherwise)

Most repos have a single context:

```
/
├── CONTEXT.md
├── docs/
│   └── adr/
│       ├── 0001-event-sourced-orders.md
│       └── 0002-postgres-for-write-model.md
└── src/
```

### Multi-module repos (like this one)

Some repos have both an overall context and per-module contexts:

```
├── CONTEXT.md                         ← overall domain context
├── UBIQUITOUS_LANGUAGE.md             ← project-wide glossary
├── docs/modules/
│   ├── cowork/
│   │   └── CONTEXT.md                 ← per-module glossary
│   └── visual-dev-tooling/
│       └── CONTEXT.md                 ← per-module glossary
```

In this pattern:
- Root `CONTEXT.md` holds cross-cutting concepts that span all modules.
- Per-module `CONTEXT.md` files hold module-specific terms and relationships.
- Root `UBIQUITOUS_LANGUAGE.md` holds the project-wide glossary.
- ADRs live at `docs/modules/<project>/adr/`.

Create files lazily — only when you have something to write. If no `CONTEXT.md` exists in the target location, create one when the first term is resolved. If no `adr/` directory exists, create it when the first ADR is needed.

## During the session

### Challenge against the glossary

When the user uses a term that conflicts with the existing language in `CONTEXT.md`, call it out immediately. "Your glossary defines 'cancellation' as X, but you seem to mean Y — which is it?"

### Sharpen fuzzy language

When the user uses vague or overloaded terms, propose a precise canonical term. "You're saying 'account' — do you mean the Customer or the User? Those are different things."

### Discuss concrete scenarios

When domain relationships are being discussed, stress-test them with specific scenarios. Invent scenarios that probe edge cases and force the user to be precise about the boundaries between concepts.

### Cross-reference with code

When the user states how something works, check whether the code agrees. If you find a contradiction, surface it: "Your code cancels entire Orders, but you just said partial cancellation is possible — which is right?"

### Update CONTEXT.md inline

When a term is resolved, update `CONTEXT.md` right there. Don't batch these up — capture them as they happen. Use the format in [CONTEXT-FORMAT.md](./CONTEXT-FORMAT.md).

### Offer ADRs sparingly

Only offer to create an ADR when all three are true:

1. **Hard to reverse** — the cost of changing your mind later is meaningful
2. **Surprising without context** — a future reader will wonder "why did they do it this way?"
3. **The result of a real trade-off** — there were genuine alternatives and you picked one for specific reasons

If any of the three is missing, skip the ADR. Use the format in [ADR-FORMAT.md](./ADR-FORMAT.md).
