---
name: to-issues
description: >
  Break a plan, spec, or PRD into independently-grabbable work slices using tracer-bullet
  vertical cuts. Each slice cuts through all layers end-to-end. Classifies slices as HITL
  (needs human interaction) or AFK (agent can implement alone). Use after to-prd when the
  user wants to break work into grabbable tickets. Use when user says "break into issues",
  "create implementation tickets", "slice this plan", or "to issues".
---

# To Issues

Break a plan into independently-grabbable work slices using vertical slices (tracer bullets).

## Process

### 1. Gather context

Work from whatever is already in the conversation context. If the user passes a GitHub issue number or URL as an argument, fetch it with `gh issue view <number>` (with comments).

### 2. Explore the codebase (optional)

If you have not already explored the codebase, do so to understand the current state of the code.

### 3. Draft vertical slices

Break the plan into **tracer bullet** slices. Each slice is a thin vertical cut that cuts through ALL integration layers end-to-end, NOT a horizontal slice of one layer.

Slices may be 'HITL' or 'AFK':
- **HITL** — requires human interaction (architectural decision, design review, approval)
- **AFK** — can be implemented and merged without human interaction

Prefer AFK over HITL where possible.

- Each slice delivers a narrow but COMPLETE path through every layer (schema, API, UI, tests)
- A completed slice is demoable or verifiable on its own
- Prefer many thin slices over few thick ones

### 4. Quiz the user

Present the proposed breakdown as a numbered list. For each slice, show:

- **Title**: short descriptive name
- **Type**: HITL / AFK
- **Blocked by**: which other slices (if any) must complete first
- **User stories covered**: which user stories this addresses (if the source material has them)

Ask the user:

- Does the granularity feel right? (too coarse / too fine)
- Are the dependency relationships correct?
- Should any slices be merged or split further?
- Are the correct slices marked as HITL and AFK?

Iterate until the user approves the breakdown.

### 5. Create the work items

Create slices in dependency order (blockers first) so you can reference real numbers in "Blocked by" fields.

**If `gh` is available and the repo uses GitHub issues**, create each slice as a GitHub issue using `gh issue create`.

**Otherwise**, write to `plans/issues/` as numbered markdown files (`001-<slug>.md`, `002-<slug>.md`, etc.). Scan for existing files and increment the number.

## Issue/slice template

```md
## Parent

# (if the source was a GitHub issue, otherwise omit this section)

## What to build

A concise description of this vertical slice. Describe the end-to-end behavior, not layer-by-layer implementation.

## Acceptance criteria

- [ ] Criterion 1
- [ ] Criterion 2
- [ ] Criterion 3

## How to verify

Evidence type: [screenshots / video / GIF / structured output / manual walkthrough]
Review method: [what the human should check when reviewing the evaluation pack]

This field is read by the `/verify` skill to determine how to produce the evaluation pack for this slice.

## Blocked by

- Blocked by #<number> (if any)

Or "None - can start immediately" if no blockers.
```

When drafting slices, propose a reasonable "How to verify" for each based on what the slice builds. The user can adjust during the quiz step.

Do NOT close or modify any parent issue.
