# Cross-Agent Skills

My personal collection of agent skills for Pi, Codex, Cursor, Droid coding agents, and future coding-agent surfaces. Matt-derived engineering skills **mirror** [mattpocock/skills](https://github.com/mattpocock/skills) at the pinned revision below. Other skills in this repo are local extensions or third-party imports, modified for my context.

This repo is the local source of truth. Global agent installs should be treated as deploy targets, not places to edit by hand.

## Upstream Status

Last synced with `mattpocock/skills` on **2026-04-29** at commit **`f71bb975bfae2dc0d31c529c7dd4a8479ecc3748`**.

- Upstream groups skills under `skills/engineering/`, `skills/productivity/`, `skills/misc/`, `skills/personal/`, and `skills/deprecated/`.
- This repo keeps **flat top-level folders** (e.g. `grill-with-docs/`, `tdd/`) so existing Codex and Cursor installs stay simple.
- **Mirrored from Matt (engineering + productivity):** `grill-with-docs`, `improve-codebase-architecture`, `tdd`, `to-issues`, `to-prd`, `zoom-out`, `caveman`, `diagnose`, `triage`, `setup-matt-pocock-skills`.
- **Removed from this repo** (deprecated upstream): `design-an-interface`, `qa`, `ubiquitous-language`. **`domain-model`** removed; its workflow is superseded by **`grill-with-docs`** (and `CONTEXT-FORMAT.md` / `ADR-FORMAT.md` beside that skill).

## Quick Start

Install the non-WIP skill folders into each global agent skill location.

- Codex: `~/.codex/skills/`
- Cursor: `~/.cursor/skills/`
- Pi: install target varies by Pi setup; use this repo as source
- Droid coding agents: install target varies by device/agent; use this repo as source

`wip-presentation/` is intentionally excluded until the presentation/PPT generation work is ready.

When adding another machine or agent, copy from this repo outward. Do not reconcile by editing the installed global copy first.

**Before** using `to-issues`, `to-prd`, `triage`, or other issue-tracker-aware skills on a new repo, run **`/setup-matt-pocock-skills`** once so `AGENTS.md` or `CLAUDE.md` and `docs/agents/` describe your tracker and triage labels.

## Skills

### Engineering (Matt-mirrored)

| Command | Purpose | Trigger |
|---|---|---|
| `/setup-matt-pocock-skills` | Scaffold `docs/agents/*` + `## Agent skills` for tracker and domain docs | First use of issue-tracker skills on a repo |
| `/grill-with-docs` | Grill a plan against `CONTEXT.md` / ADRs; update glossary and docs inline | Stress-test a plan; align language and decisions |
| `/to-prd` | Turn conversation + codebase understanding into a PRD on the issue tracker | Ready to publish a PRD |
| `/to-issues` | Break a plan into vertical tracer-bullet issues | Have a spec; need tickets |
| `/triage` | Move issues through triage state machine | Triage or prep issues for agents |
| `/tdd` | Red-green-refactor with vertical slices | Building or fixing with tests |
| `/improve-codebase-architecture` | Find deepening opportunities; align with CONTEXT + ADRs | Refactor / architecture survey |
| `/diagnose` | Reproduce → hypothesise → instrument → fix for hard bugs | Broken behaviour or perf regression |
| `/zoom-out` | One-level-up map using domain vocabulary | Lost in the weeds |

### Local extensions

These are **not** from Matt’s engineering set but are part of this repo’s operating system.

| Command | Purpose | Trigger |
|---|---|---|
| `/prototype-data` | Generate structured JSON data model | Define what the feature IS |
| `/prototype-artifact` | Visualize data (flows, mockups) | Have JSON; want visuals |
| `/verify` | Evidence pack + HTML report | After building; need proof |
| `/postmortem` | Compound learnings into `AGENTS.md` / rules | End of session |

### Productivity and design

| Command | Purpose | Trigger |
|---|---|---|
| `/caveman` | Compressed chat mode (~75% fewer tokens) | Terse replies |
| `/design-motion-principles` | Motion and interaction audit | UI motion review |
| `/emil-design-eng` | UI polish and craft | Design-engineering taste |
| `/familiar` | Recent screen/session context (Familiar) | Recall on-screen work |

### Upstream not imported (optional review)

Skills that exist under Matt’s `skills/misc/` or `skills/personal/` are not copied here by default (e.g. `write-a-skill`, `git-guardrails-claude-code`, `obsidian-vault`). Add them only if you want them on your machines.

## Flow Map

```
BUILD LOOP
  /grill-with-docs → [/prototype-data → /prototype-artifact] → /to-prd → /to-issues → /tdd
                                                                                        │
                                                                                        ▼
VERIFICATION LOOP
  /verify → /postmortem ───────────────────────────────────────────────────────────────┘
                                                                                        │
                                                                                        ▼
FEEDBACK LOOP
  /triage / /diagnose / new issues ──→ back to /grill-with-docs (or /tdd) for the fix cycle
```

The full ASCII flow lives in [`MAP/skills-flow.md`](MAP/skills-flow.md). Inventory: [`MAP/skills-readme.md`](MAP/skills-readme.md).

## Principles

- **Repo first.** This repo is canonical. Installs are deploy targets.
- **Verification-first.** Slices carry “How to verify”; `/verify` proves it.
- **Compound learning.** Postmortems write back into repo instructions.
- **Tracer-bullet cuts.** Vertical slices through all layers.
- **Matt parity for mirrored skills.** Engineering skills listed above match Matt’s repo at the pinned commit (paths like `../grill-with-docs/` stay valid in this flat layout).

## Structure

```
skills repo source/
├── MAP/
│   ├── skills-flow.md
│   └── skills-readme.md
├── caveman/SKILL.md
├── design-motion-principles/
│   ├── SKILL.md
│   └── references/
├── diagnose/
│   ├── SKILL.md
│   └── scripts/hitl-loop.template.sh
├── emil-design-eng/SKILL.md
├── familiar/SKILL.md
├── grill-with-docs/
│   ├── SKILL.md
│   ├── CONTEXT-FORMAT.md
│   └── ADR-FORMAT.md
├── improve-codebase-architecture/
│   ├── SKILL.md
│   ├── DEEPENING.md
│   ├── INTERFACE-DESIGN.md
│   └── LANGUAGE.md
├── postmortem/SKILL.md
├── prototype-artifact/SKILL.md
├── prototype-data/SKILL.md
├── setup-matt-pocock-skills/
│   ├── SKILL.md
│   ├── domain.md
│   ├── issue-tracker-github.md
│   ├── issue-tracker-gitlab.md
│   ├── issue-tracker-local.md
│   └── triage-labels.md
├── tdd/
│   ├── SKILL.md
│   ├── deep-modules.md
│   ├── interface-design.md
│   ├── mocking.md
│   ├── refactoring.md
│   └── tests.md
├── to-issues/SKILL.md
├── to-prd/SKILL.md
├── triage/
│   ├── SKILL.md
│   ├── AGENT-BRIEF.md
│   └── OUT-OF-SCOPE.md
├── verify/SKILL.md
├── zoom-out/SKILL.md
├── CHANGELOG.md
├── TODO.md
└── wip-presentation/          # excluded from global sync for now
```

## Sync Policy

1. Pull Matt changes; diff mirrored skill folders.
2. Update this repo; record in `CHANGELOG.md`.
3. Sync outward to `~/.codex/skills/` and `~/.cursor/skills/`.
4. `diff -qr` repo folder vs install for each synced skill.

## License

MIT
