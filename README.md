# Cross-Agent Skills

My personal collection of agent skills for Pi, Codex, Cursor, Droid coding agents, and future coding-agent surfaces. Shaped and inspired by https://github.com/mattpocock/skills/tree/main and practices from others, modified and used for my context.

This repo is the local source of truth. Global agent installs should be treated as deploy targets, not places to edit by hand.

## Upstream Status

Last checked against `mattpocock/skills` on 2026-04-28.

- Upstream latest checked commit: `c21cf6ec93b4a25a5118a1a600ebb777e50d6c2e`
- Upstream now groups skills under `engineering/`, `productivity/`, `misc/`, `personal/`, and `deprecated/`
- Upstream renamed the active domain-doc grilling skill to `grill-with-docs`; this repo currently keeps the local command name `/domain-model`
- Local folders stay flat for now so existing Codex and Cursor installs keep working
- Upstream-deprecated skills are marked below before removal, because this repo has local workflows that may still depend on them

## Quick Start

Install the non-WIP, non-deprecated skill folders into each global agent skill location.

- Codex: `~/.codex/skills/`
- Cursor: `~/.cursor/skills/`
- Pi: install target varies by Pi setup; use this repo as source
- Droid coding agents: install target varies by device/agent; use this repo as source

`wip-presentation/` is intentionally excluded until the presentation/PPT generation work is ready.

When adding another machine or agent, copy from this repo outward. Do not reconcile by editing the installed global copy first.

## Skills

### Engineering

Core code-work skills. These are closest to upstream's active `engineering` bucket.

| Command | Purpose | Trigger |
|---|---|---|
| `/domain-model` | Define the domain — glossary, ADRs, CONTEXT.md. Local name for upstream `grill-with-docs` behavior | Starting a new project or module |
| `/to-prd` | Synthesize decisions into a PRD | Decisions converged, time to spec |
| `/to-issues` | Slice PRD into vertical work tickets | Have a PRD, ready to break into work |
| `/tdd` | Red-green-refactor build loop | Have issues, time to code |
| `/improve-codebase-architecture` | Survey for shallow modules and friction | Inherited a codebase |
| `/zoom-out` | One-level-up code context map | Deep in a file, lost the neighborhood |

### Local Extensions

These are local workflow skills that do not currently come from `mattpocock/skills`, but are part of this repo's operating system.

| Command | Purpose | Trigger |
|---|---|---|
| `/prototype-data` | Generate structured JSON data model | Need to define what the feature IS |
| `/prototype-artifact` | Visualize data as flowcharts, mockups | Have JSON data, want visual reference |
| `/verify` | Generate evidence pack — prove it works | After building a feature |
| `/postmortem` | Compound learnings into persistent rules | After a session wraps up |

### Productivity And Design

Anytime. No fixed position in the flow.

| Command | Purpose | Trigger |
|---|---|---|
| `/caveman` | Compressed chat mode (~75% fewer tokens) | Want terse output |
| `/grill-me` | Interrogate a plan — one question at a time | Have a rough idea, need to converge |
| `/design-motion-principles` | Context-aware motion and interaction design audit | Reviewing UI animations and transitions |
| `/emil-design-eng` | UI polish, component craft, and animation review | Need design-engineering taste checks |
| `/familiar` | Reconstruct recent on-screen work from Familiar stills | Need recent screen/session context |

### Deprecated / Review Before Sync

These are kept locally for continuity, but should not be installed to new agent surfaces without an explicit decision.

| Command | Reason |
|---|---|
| `/design-an-interface` | Deprecated upstream on 2026-04-28; local workflow overlap with architecture and planning skills |
| `/qa` | Deprecated upstream on 2026-04-28; local workflow may still be useful for conversational issue capture |
| `/ubiquitous-language` | Deprecated upstream on 2026-04-28; local workflow overlaps with `/domain-model` |

### Upstream Candidates Not Yet Imported

These exist upstream and should be reviewed before the next cross-agent sync.

| Skill | Upstream bucket | Initial local stance |
|---|---|---|
| `grill-with-docs` | engineering | Rename candidate; local `/domain-model` already covers this behavior, so decide before adding a duplicate command |
| `diagnose` | engineering | Strong candidate; likely useful for hard bugs and regression loops |
| `github-triage` | engineering | Candidate if GitHub issue labels become part of the shared workflow |
| `write-a-skill` | productivity | Strong candidate because this repo will keep receiving updates |
| `git-guardrails-claude-code` | misc | Maybe; likely Claude-specific, adapt only if useful outside Claude |
| `migrate-to-shoehorn` | misc | Maybe; TypeScript-specific and narrow |
| `scaffold-exercises` | misc | Maybe; useful only for course/exercise repos |
| `setup-pre-commit` | misc | Maybe; useful but repo/project-specific |
| `edit-article` | personal | Do not import by default; overlaps with local writing/editing workflows |
| `obsidian-vault` | personal | Do not import by default; personal setup-specific |

## Flow Map

```
BUILD LOOP
  /domain-model → /grill-me → [/prototype-data → /prototype-artifact] → /to-prd → /to-issues → /tdd
                                                                                                  │
                                                                                                  ▼
VERIFICATION LOOP
  /verify → /postmortem ──────────────────────────────────────────────────────────────────────────┘
                                                                                                  │
                                                                                                  ▼
FEEDBACK LOOP
  /qa (legacy/deprecated) ──→ back to /grill-me for the fix cycle
```

The full ASCII flow map with verification-first detail lives in [`MAP/skills-flow.md`](MAP/skills-flow.md). A detailed inventory of every skill is in [`MAP/skills-readme.md`](MAP/skills-readme.md).

## Principles

- **Repo first.** This repo is canonical. Pi, Codex, Cursor, Droid, and future agent installs are deploy targets.
- **Verification-first.** Define how to verify before building. Each work slice carries its own "How to verify" field.
- **Compound learning.** Postmortems write back to persistent repo instructions. The repo gets smarter every session.
- **Tracer-bullet cuts.** Every slice goes end-to-end. No horizontal layer-by-layer work.
- **Human at the seams.** Skills classify work as HITL (human-in-the-loop) or AFK (agent can run alone). Humans approve learning proposals before they're applied.
- **Upstream-aware, locally-owned.** Upstream changes are reviewed and adapted; they are not blindly mirrored.

## Structure

```
skills repo source/
├── MAP/                              # Human reference maps
│   ├── skills-flow.md                # ASCII flow diagrams
│   └── skills-readme.md              # Detailed skill inventory
├── caveman/SKILL.md
├── design-an-interface/SKILL.md
├── design-motion-principles/
│   ├── SKILL.md
│   └── references/
├── domain-model/SKILL.md
│   ├── CONTEXT-FORMAT.md
│   └── ADR-FORMAT.md
├── emil-design-eng/SKILL.md
├── familiar/SKILL.md
├── grill-me/SKILL.md
├── improve-codebase-architecture/
│   ├── SKILL.md
│   ├── DEEPENING.md
│   ├── INTERFACE-DESIGN.md
│   └── LANGUAGE.md
├── postmortem/SKILL.md
├── prototype-artifact/SKILL.md
├── prototype-data/SKILL.md
├── qa/SKILL.md
├── tdd/
│   ├── SKILL.md
│   ├── deep-modules.md
│   ├── interface-design.md
│   ├── mocking.md
│   ├── refactoring.md
│   └── tests.md
├── to-issues/SKILL.md
├── to-prd/SKILL.md
├── ubiquitous-language/SKILL.md
├── verify/SKILL.md
├── zoom-out/SKILL.md
├── CHANGELOG.md
└── wip-presentation/                 # Excluded from global sync for now
```

## Sync Policy

1. Review upstream changes first, especially renamed buckets, deprecations, and new skills.
2. Update this repo's skill files and docs.
3. Record the decision in `CHANGELOG.md`.
4. Sync outward to installed agent locations.
5. Verify installed folders match this repo for all active synced skills.

Deprecated and WIP folders are excluded from fresh installs unless a specific machine or agent needs them.

## License

MIT
