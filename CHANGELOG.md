# Changelog

This repo is the canonical source for the user's cross-agent skills. Installed copies for Pi, Codex, Cursor, Droid coding agents, and future agent surfaces should be synced from here.

## 2026-04-28

### Second Upstream Review

- Re-checked `mattpocock/skills` at commit `c21cf6ec93b4a25a5118a1a600ebb777e50d6c2e`.
- Confirmed upstream changed the active domain-doc grilling skill from `domain-model` to `grill-with-docs`.
- Kept this repo's local `/domain-model` command for now because it already carries the same workflow and is embedded in the local build loop.
- Added `grill-with-docs` as a rename candidate rather than importing it blindly as a duplicate.
- Confirmed upstream deprecated skills remain:
  - `design-an-interface`
  - `qa`
  - `ubiquitous-language`
- No new local skill folders were added during this pass.

### Upstream Review

- Checked `mattpocock/skills` at commit `71542f9d1cc45dc9c84c99e43d6c6bcc4fc523d7`.
- Noted upstream's structural change from a flat catalog to grouped buckets:
  - `skills/engineering/`
  - `skills/productivity/`
  - `skills/misc/`
  - `skills/personal/`
  - `skills/deprecated/`
- Kept this repo's local folder layout flat for now to avoid breaking existing Codex and Cursor installs.

### README

- Reframed the repo from "Codex and Cursor Skills" to "Cross-Agent Skills".
- Documented this repo as the source of truth for Pi, Codex, Cursor, Droid coding agents, and future coding-agent surfaces.
- Added upstream check metadata and a sync policy.
- Split the skill list into:
  - Engineering
  - Local Extensions
  - Productivity And Design
  - Deprecated / Review Before Sync
  - Upstream Candidates Not Yet Imported

### Deprecation Review

- Marked these local skills as deprecated or review-before-sync because upstream now places them under `skills/deprecated/`:
  - `design-an-interface`
  - `qa`
  - `ubiquitous-language`
- Kept them in the repo for continuity until their local usage is reviewed.

### Upstream Candidates

- Identified active upstream skills missing locally:
  - `diagnose`
  - `github-triage`
  - `write-a-skill`
  - `git-guardrails-claude-code`
  - `migrate-to-shoehorn`
  - `scaffold-exercises`
  - `setup-pre-commit`
- Identified upstream personal skills that should not be imported by default:
  - `edit-article`
  - `obsidian-vault`

### Known Follow-Up

- Decide whether to import `diagnose` and `write-a-skill` first.
- Decide whether deprecated local skills should be moved into a `deprecated/` folder or only excluded from sync.
- Update `MAP/skills-readme.md` after the active/deprecated split is finalized.
- Create or update a sync script once Pi and Droid agent install paths are known.

## 2026-04-27

- Synced non-WIP repo skills into Codex and Cursor global skill folders.
- Added `familiar` to both install targets.
- Kept `wip-presentation/` excluded until the presentation/PPT skill is ready.
- Added upstream `emil-design-eng` from `emilkowalski/skill`.
- Added upstream `design-motion-principles` from `kylezantos/design-motion-principles`.

## 2026-04-19

- Created `/verify` and `/postmortem` skills.
- Enhanced `/to-issues` with a "How to verify" field.
- Enhanced `/tdd` with visual checkpoint after GREEN.
- Updated the skill inventory.
