---
name: grill-me
description: >
  Relentless one-at-a-time interrogation of a plan, PRD, or task design. Walks the
  decision tree, resolves dependencies between decisions, recommends answers. Use for
  "what do we BUILD in this world?" — feature plans, PRDs, task scoping, sequencing
  decisions, edge-case discovery. Use when user says "grill me", "stress-test this plan",
  "challenge this design", or wants to sharpen a specific piece of work before execution.
disable-model-invocation: true
---

Interview me relentlessly about every aspect of this plan until we reach a shared understanding. Walk down each branch of the design tree, resolving dependencies between decisions one-by-one. For each question, provide your recommended answer.

Ask the questions one at a time, waiting for feedback on each question before continuing.

If a question can be answered by exploring the codebase or existing docs, explore instead of asking.

## What this skill is for

This is the "what do we BUILD?" skill. You have a domain, a context, a world that's already defined. Now you have a specific thing to build — a feature, a module, a system, a document. This skill grills you until the plan is sharp enough to execute.

## During the session

### Resolve ambiguity before complexity

If the plan uses terms that aren't clearly defined, resolve the terms first. If the project has a CONTEXT.md, use it. If not, ask: "What do you mean by X?"

### Challenge sequencing

If step B depends on step A, ask about A first. Don't let the user skip ahead to interesting parts while foundations are undecided.

### Invent edge cases

When the user describes happy paths, propose specific scenarios that break assumptions. "What happens when X fails mid-way? What if Y happens twice? What if Z is null?"

### Surface hidden dependencies

If the plan touches other modules, systems, or people, call it out. "This requires the auth service to support X — does it? Who owns that? Have you talked to them?"

### Produce the artifact

When the grilling converges, write the plan/PRD to the appropriate location:
- Repo plans → `plans/<slug>.md`
- Module-specific → `docs/modules/<project>/`
- Follow the repo's AGENTS.md conventions for placement

Don't batch insights — capture decisions as they crystallize into the artifact.
