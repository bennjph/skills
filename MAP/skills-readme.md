# Skills Inventory

> This folder is for the human. It holds reference maps of the skill system — what each skill does, when to use it, and how they connect.

All skills live in `~/.cursor/skills/`. Each is triggered by slash command (e.g. `/grill-me`, `/tdd`). The agent reads the skill file and follows its instructions for the duration of that session.

---

## Build Loop

The main sequence. Walk through these in order for new features or modules.

### 1. `/domain-model` — "What IS this world?"

Define the domain before you build in it. Produces a `CONTEXT.md` glossary and ADRs (architecture decision records) that enforce consistent terminology. The agent checks these on future sessions.

**Output:** `CONTEXT.md` (root and/or per-module), `UBIQUITOUS_LANGUAGE.md` (root), ADRs in `docs/modules/<project>/adr/`

### 2. `/grill-me` — "What do we BUILD?"

Relentless one-at-a-time interrogation of a plan or feature. Walks the decision tree, resolves dependencies, surfaces edge cases, recommends answers. The agent explores the codebase instead of asking questions it can answer itself.

**Output:** Converged plan written to `plans/<slug>.md` or `docs/modules/<project>/`

### 3. `/prototype-data` — "Define the feature's data" *(optional)*

Generate a structured JSON data model with realistic sample data. Defines what the feature *is* before rendering how it looks. Flows, screens, entities, timing — all in JSON.

**Output:** JSON file in `plans/` or `docs/modules/<project>/`

### 4. `/prototype-artifact` — "Visualize it" *(optional)*

Take the JSON from `/prototype-data` and render it as flowcharts, mockups, or timing diagrams. Output goes to Canvas, standalone HTML, or a React app. Visual reference for the PRD, not a replacement.

**Output:** Visual artifact (Canvas, HTML, or React app)

### 5. `/to-prd` — "Write it down"

Synthesize converged decisions into a structured PRD. Pulls from `grill-me` output, prototype artifacts, and domain context. The written specification that implementation tracks against.

**Output:** PRD in `plans/<slug>.md`

### 6. `/to-issues` — "Break into work"

Slice the PRD into vertical tracer-bullet cuts. Each slice goes end-to-end through all layers. Classified as HITL (needs human interaction) or AFK (agent can implement alone). Each slice includes a **"How to verify" field** that specifies the evidence type and review method before work starts — this is the pre-commit verification step that `/verify` reads later.

**Output:** GitHub issues or `plans/issues/<NNN>-<slug>.md` markdown files

### 7. `/tdd` — "Build it"

Red-green-refactor loop. One test → one implementation → repeat. Tests verify behavior through public interfaces, not implementation details. After each GREEN cycle, a **visual checkpoint** captures what was built (screenshot for UI, test output for non-UI) — temporary, not saved to `proofs/`, catches broken rendering early.

**Output:** Working code with passing tests

---

## Verification Loop

After building. Manually invoked.

### 8. `/verify` — "Prove it works"

Generate an evaluation pack for whatever was just built. The agent captures evidence (screenshots, video, GIF, structured output), reviews its own output, fixes issues it catches, then packages everything into an HTML report. The human reviews the report and adds feedback.

**Evidence types by task:**

| Task kind             | Evidence                                 |
| --------------------- | ---------------------------------------- |
| UI interactive flow   | Video + screenshots                      |
| UI sequential actions | GIF of action sequence + screenshots     |
| UI static             | Screenshots                              |
| API / CLI             | Structured test output, fixture captures |
| Docs                  | Rendered diff summary                    |

**Output:** HTML evaluation pack in `proofs/`, agent findings, human review comments

### 9. `/postmortem` — "What did we learn?"

Reflect on the session and compound learnings into persistent instructions. The agent reviews what happened, collects human input, identifies patterns (DO / DON'T / WHEN), and proposes concrete edits to `AGENTS.md`, `.cursor/rules/`, or subdirectory instructions. Human approves each change before it's applied.

The Marble Madness principle: the repo is the level, the agent is the marble. Shape the level so the next run is smoother.

**Output:** Edits to `AGENTS.md` (repo root or subdirectory) and `LEARNINGS.md` (process observations at root).

---

## Feedback Loop

After shipping. Catches what slipped through.

### 10. `/qa` — "What's broken?"

Conversational bug reporting. Describe problems in natural language, the agent clarifies, explores the codebase for context, and files durable issues. Issues feed back into `/grill-me` for the fix cycle.

**Output:** GitHub issues or `plans/issues/` markdown files

---

## Retrofit Loop

When existing code needs improvement, not new features.

### 11. `/improve-codebase-architecture` — "What's shallow?"

Survey the codebase for architectural friction. Find shallow modules, propose deepening. Identify testability gaps and coupling problems.

**Output:** GitHub issues or `plans/issues/` markdown files

### 12. `/design-an-interface` — "Design competing boundaries"

Generate 3+ radically different interface designs for a module using parallel sub-agents. Compare tradeoffs, pick the best shape.

**Output:** Interface comparison document in `plans/<module-slug>-interface-comparison.md`

---

## Ad-hoc

Anytime. No fixed position in the flow.

### 13. `/caveman` — Compressed chat mode

Drops filler, articles, and pleasantries. Full technical accuracy, ~75% fewer tokens. Chat output only — file output follows AGENTS.md Writing Doctrine.

### 14. `/ubiquitous-language` — Batch glossary extraction

Extract domain terms from the conversation into `UBIQUITOUS_LANGUAGE.md` at the repo root. Lighter than `/domain-model` for quick glossary snapshots.

### 15. `/zoom-out` — Code context map

One-level-up view of where a code area fits. Inbound dependencies, outbound calls, sibling modules, data flow. Useful when you're deep in a file and need to remember the neighborhood.

---

## Skill File Locations

| #   | Skill                         | Directory                                         | Files                                                                                |
| --- | ----------------------------- | ------------------------------------------------- | ------------------------------------------------------------------------------------ |
| 1   | caveman                       | `~/.cursor/skills/caveman/`                       | SKILL.md                                                                             |
| 2   | ubiquitous-language           | `~/.cursor/skills/ubiquitous-language/`           | SKILL.md                                                                             |
| 3   | zoom-out                      | `~/.cursor/skills/zoom-out/`                      | SKILL.md                                                                             |
| 4   | domain-model                  | `~/.cursor/skills/domain-model/`                  | SKILL.md, CONTEXT-FORMAT.md, ADR-FORMAT.md                                           |
| 5   | grill-me                      | `~/.cursor/skills/grill-me/`                      | SKILL.md                                                                             |
| 6   | prototype-data                | `~/.cursor/skills/prototype-data/`                | SKILL.md                                                                             |
| 7   | prototype-artifact            | `~/.cursor/sskills/prototype-artifact/`           | SKILL.md                                                                             |
| 8   | to-prd                        | `~/.cursor/skills/to-prd/`                        | SKILL.md                                                                             |
| 9   | to-issues                     | `~/.cursor/skills/to-issues/`                     | SKILL.md                                                                             |
| 10  | tdd                           | `~/.cursor/skills/tdd/`                           | SKILL.md, deep-modules.md, interface-design.md, mocking.md, refactoring.md, tests.md |
| 11  | verify                        | `~/.cursor/skills/verify/`                        | SKILL.md                                                                             |
| 12  | postmortem                    | `~/.cursor/skills/postmortem/`                    | SKILL.md                                                                             |
| 13  | qa                            | `~/.cursor/skills/qa/`                            | SKILL.md                                                                             |
| 14  | improve-codebase-architecture | `~/.cursor/skills/improve-codebase-architecture/` | SKILL.md, REFERENCE.md                                                               |
| 15  | design-an-interface           | `~/.cursor/skills/design-an-interface/`           | SKILL.md                                                                             |

---

## Change Log

- 2026-04-19 — Created `/verify` and `/postmortem` skills. Enhanced `/to-issues` with "How to verify" field. Enhanced `/tdd` with visual checkpoint after GREEN. Updated skill file locations table (all 15 skills now exist).
