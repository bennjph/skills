# Skills Inventory

> This folder is for the human. It holds reference maps of the skill system — what each skill does, when to use it, and how they connect.

Synced skills live in both `~/.codex/skills/` and `~/.cursor/skills/`. Each is triggered by slash command or skill name where the agent supports skills. The agent reads the skill file and follows its instructions for the duration of that session.

`wip-presentation/` is not part of the global sync yet. Keep it as a repo-local WIP area until the presentation/PPT generation skill is ready.

---

## Setup (once per target repo)

### `/setup-matt-pocock-skills` — Issue tracker + triage + domain layout

Scaffolds `docs/agents/issue-tracker.md`, `docs/agents/triage-labels.md`, `docs/agents/domain.md`, and an `## Agent skills` block in `CLAUDE.md` or `AGENTS.md`. Run before relying on `to-issues`, `to-prd`, or `triage` on that repo.

---

## Build loop

The main sequence for new features or modules.

### 1. `/grill-with-docs` — Converge the plan and the language

Stress-test the plan against existing `CONTEXT.md` and ADRs. One question at a time; update the glossary inline; offer ADRs only when Matt’s three criteria apply. Replaces the former `/domain-model` + short `/grill-me` split.

**Output:** Updated `CONTEXT.md`, occasional new ADRs, sharper decisions in conversation / `plans/`.

### 2. `/prototype-data` — "Define the feature's data" *(optional)*

Generate a structured JSON data model with realistic sample data.

**Output:** JSON file in `plans/` or project docs.

### 3. `/prototype-artifact` — "Visualize it" *(optional)*

Render JSON as flowcharts, mockups, or timing diagrams.

**Output:** Visual artifact (Canvas, HTML, or React app).

### 4. `/to-prd` — "Write it down"

Publish a PRD to the **configured issue tracker** (not GitHub-only — see setup skill). Uses domain vocabulary and ADRs in the area you touch.

**Output:** Tracker issue + template sections from the skill.

### 5. `/to-issues` — "Break into work"

Vertical tracer-bullet slices with HITL/AFK and **"How to verify"** per slice.

**Output:** Tracker issues.

### 6. `/tdd` — "Build it"

Red-green-refactor in vertical slices. Planning step references domain glossary and ADRs.

**Output:** Code + tests.

---

## Verification loop

After building. Manually invoked.

### 7. `/verify` — "Prove it works"

Evidence pack (screenshots, video, GIF, structured output), self-review, HTML report under `proofs/`.

### 8. `/postmortem` — "What did we learn?"

Compound DO / DON'T / WHEN into `AGENTS.md`, `.cursor/rules/`, etc., with human approval.

---

## Feedback and maintenance loop

### `/triage` — Issue workflow

Move issues through triage roles; optional `/grill-with-docs` when an issue needs fleshing out. Uses label vocabulary from setup.

### `/diagnose` — Hard bugs and regressions

Build a feedback loop, reproduce, rank hypotheses, instrument, fix + regression test, cleanup.

### `/improve-codebase-architecture` — "What's shallow?"

Survey coupling and shallow modules; grilling loop can update `CONTEXT.md` and suggest ADRs per Matt’s patterns.

**Output:** Candidates and optional tracker follow-ups.

---

## Ad-hoc

Anytime. No fixed position in the flow.

### `/caveman` — Compressed chat mode

~75% fewer tokens; technical accuracy preserved.

### `/emil-design-eng` — Design engineering polish

### `/design-motion-principles` — Motion design audit

### `/familiar` — Recent screen/session context

### `/zoom-out` — Code context map

Uses the project's domain glossary in Matt’s upstream wording.

---

## Skill file locations

| # | Skill | Installed directory suffix | Files |
| --- | --- | --- | --- |
| 1 | caveman | `caveman/` | SKILL.md |
| 2 | diagnose | `diagnose/` | SKILL.md, scripts/hitl-loop.template.sh |
| 3 | emil-design-eng | `emil-design-eng/` | SKILL.md |
| 4 | familiar | `familiar/` | SKILL.md |
| 5 | design-motion-principles | `design-motion-principles/` | SKILL.md, references/*.md |
| 6 | grill-with-docs | `grill-with-docs/` | SKILL.md, CONTEXT-FORMAT.md, ADR-FORMAT.md |
| 7 | improve-codebase-architecture | `improve-codebase-architecture/` | SKILL.md, DEEPENING.md, INTERFACE-DESIGN.md, LANGUAGE.md |
| 8 | postmortem | `postmortem/` | SKILL.md |
| 9 | prototype-artifact | `prototype-artifact/` | SKILL.md |
| 10 | prototype-data | `prototype-data/` | SKILL.md |
| 11 | setup-matt-pocock-skills | `setup-matt-pocock-skills/` | SKILL.md, domain.md, issue-tracker-*.md, triage-labels.md |
| 12 | tdd | `tdd/` | SKILL.md, deep-modules.md, interface-design.md, mocking.md, refactoring.md, tests.md |
| 13 | to-issues | `to-issues/` | SKILL.md |
| 14 | to-prd | `to-prd/` | SKILL.md |
| 15 | triage | `triage/` | SKILL.md, AGENT-BRIEF.md, OUT-OF-SCOPE.md |
| 16 | verify | `verify/` | SKILL.md |
| 17 | zoom-out | `zoom-out/` | SKILL.md |

Install each suffix under both `~/.codex/skills/` and `~/.cursor/skills/`.

---

## Change log

- **2026-04-29** — Synced Matt engineering skills: `grill-with-docs` (replaced `grill-me` + removed `domain-model`), added `diagnose`, `triage`, `setup-matt-pocock-skills`; removed deprecated `design-an-interface`, `qa`, `ubiquitous-language`. Updated this inventory and flow docs.
- 2026-04-19 — Created `/verify` and `/postmortem`. Enhanced `/to-issues` with "How to verify". Enhanced `/tdd` with visual checkpoint after GREEN.
- 2026-04-27 — Synced repo skills into Codex and Cursor; added `/familiar`.
- 2026-04-27 — Added `/emil-design-eng` and `/design-motion-principles`.
