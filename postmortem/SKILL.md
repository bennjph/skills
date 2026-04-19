---
name: postmortem
description: >
  Reflect on a completed session and compound learnings into persistent instruction files.
  The agent reviews what happened, collects human input, identifies DO/DON'T/WHEN patterns,
  and proposes concrete edits to AGENTS.md, LEARNINGS.md, or subdirectory instruction files.
  Human approves each change before it is applied. The Marble Madness principle: shape the
  repo (the level) so the next agent run (the marble) reaches the goal more smoothly.
  Slash-command only — `/postmortem`. Most powerful after `/verify` but works after any session.
disable-model-invocation: true
---

# Postmortem — "What did we learn?"

Reflect on the session and write learnings into the repo's persistent files so the next run starts smarter.

This is the compounded learning mechanism. Without it, every agent run starts from the same baseline. With it, the repo accumulates knowledge about what works, what doesn't, and what to watch for.

## When to use this skill

After any session where something notable happened. Most useful after `/verify` (richest context) but works after any work session.

```
BUILD:      ... → tdd → ship
VERIFY:                      /verify → (human reviews)
LEARN:                                          /postmortem → (edits AGENTS.md + LEARNINGS.md)
```

The postmortem fires once per session. It does not replace `qa` (bug capture) or `improve-codebase-architecture` (structural survey). It captures workflow and navigation learnings specific to how this repo should be worked with.

## What counts as a learning

Three categories:

- **DO** — a pattern that worked well and should be repeated. *"Running the linter before committing caught 3 issues early."*
- **DON'T** — a pattern that caused problems. *"Don't try to refactor `modules/cowork/research/` and `docs/modules/cowork/product/` in the same session — they have hidden coupling through CONTEXT.md."*
- **WHEN** — conditional guidance. *"When working in `code/website/`, always check `package.json` for script names before running build commands — the names are non-standard."*

A learning is only worth writing down if it changes future behavior. If it's obvious, generic, or already in the instructions, skip it.

## Step 1: Reflect on the session

Review what happened in this conversation:

- What tool calls were made? What paths did the agent explore?
- Were there dead ends, rework cycles, or misunderstandings?
- Did the agent take a surprising or inefficient path? Why?
- What in the repo made that path likely?

If the session included `/verify`:
- Review the evaluation pack findings
- Review what the human caught that the agent missed
- Note any friction in the verification process itself

If the session did not include `/verify`:
- Work from the conversation transcript and the work that was done
- Focus on workflow friction, not verification gaps

Ask yourself: *"If I started this exact same task tomorrow with a fresh context window, what would I want to already know?"*

## Step 2: Collect human input

Ask the human:

1. *"What caught your eye during this session — good or bad?"*
2. *"What should the agent have done differently?"*
3. *"Anything surprise you?"*

Keep this brief. 2-3 questions, let the human answer in their own words. Don't interrogate.

If the human just ran `/verify` and gave feedback, incorporate that feedback here. Don't re-ask the same questions.

## Step 3: Identify learnings

From the reflection (step 1) and human input (step 2), extract concrete learnings.

**Good learnings:**
- Specific to this repo or project
- Actionable — a future agent can follow the advice
- Non-obvious — not something the agent would figure out from reading the code alone

**Bad learnings (skip these):**
- Generic advice ("write good code")
- Already in AGENTS.md
- Too specific to one moment ("the file was locked") without a generalizable lesson

Classify each learning as DO, DON'T, or WHEN.

## Step 4: Propose instruction changes

For each learning, propose a specific edit to a specific file.

**Where learnings go:**

| Target | When to use | Agent reads automatically? |
|---|---|---|
| `AGENTS.md` (repo root) | Cross-project workflow rules, warnings, patterns | Yes — every session |
| `AGENTS.md` (subdirectory) | Module-specific patterns | Yes — when working in that directory |
| `LEARNINGS.md` (repo root) | Process improvements worth keeping but not yet encoded as rules | Yes — lives at root |
| `sessions/context.md` | Session-to-session memory, ongoing investigations | Partial — agent may check it |

**How to choose between AGENTS.md and LEARNINGS.md:**
- If the learning changes how every agent session should behave → `AGENTS.md`
- If the learning is a process observation, a "we tried this and it worked/didn't" note, or something to review later → `LEARNINGS.md`
- Over time, patterns in LEARNINGS.md that prove durable should be promoted into AGENTS.md

For each proposed change, show:

```
LEARNING: [the DO/DON'T/WHEN pattern]
TARGET:   [which file to edit]
CHANGE:   [exact proposed addition or edit]
REASON:   [why this will help future runs]
```

Present all proposals together. Do not apply any yet.

## Step 5: Get human approval

Walk through each proposal with the human. For each:

- Explain the learning and why it matters
- Show the proposed edit
- Ask: *"Include this?"*

The human can:
- **Approve** — apply as proposed
- **Modify** — adjust the wording, target file, or scope
- **Reject** — skip this learning entirely

Do not batch-approve. Each change is independent.

## Step 6: Apply approved changes

For each approved change:
1. Read the target file
2. Apply the edit in the right location (respect existing structure and tone)
3. Confirm the edit was applied correctly

After all changes are applied, summarize:

```
Applied [X] instruction changes:
- [file]: [brief summary of what was added/changed]
- [file]: [brief summary]
...
```

## Step 7: Update session context

If `sessions/context.md` exists, add a brief note about this postmortem:

```
- YYYY-MM-DD: [what was learned, in one sentence]
```

This creates a lightweight log of compounded learnings over time.

## Rules

- **Only write non-obvious learnings.** If the agent would figure it out from the code alone, don't clutter the instructions.
- **Propose, don't apply.** Every change gets human approval first.
- **Target the right file.** Rules → `AGENTS.md`. Process observations → `LEARNINGS.md`. Module-specific → subdirectory `AGENTS.md`.
- **Keep edits minimal.** Add sentences or bullet points, not paragraphs. Instruction files should stay scannable.
- **Don't duplicate.** If the rule already exists in the instructions (even in different words), don't add it again. Strengthen the existing rule instead.
- **Write for the next agent.** The audience is a fresh agent with no context about this session. Be specific, be concrete, be brief.
