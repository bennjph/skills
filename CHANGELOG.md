# Changelog

This repo is the canonical source for the user's cross-agent skills. Installed copies for Pi, Codex, Cursor, Droid coding agents, and future agent surfaces should be synced from here.

## 2026-04-29

### Matt sync (mirror engineering + productivity)

- Synced from `mattpocock/skills` at commit `f71bb975bfae2dc0d31c529c7dd4a8479ecc3748`.
- **Renamed / replaced:** `grill-me/` → `grill-with-docs/` (upstream `skills/engineering/grill-with-docs`), including `CONTEXT-FORMAT.md` and `ADR-FORMAT.md`.
- **Updated to match Matt:** `improve-codebase-architecture/`, `tdd/`, `to-issues/`, `to-prd/`, `zoom-out/`, `caveman/`.
- **Added:** `diagnose/` (with `scripts/hitl-loop.template.sh`), `triage/`, `setup-matt-pocock-skills/`.
- **Removed:** `domain-model/`, `design-an-interface/`, `qa/`, `ubiquitous-language/` (deprecated or superseded upstream).
- **Docs:** Rewrote `README.md`, `MAP/skills-readme.md`, `MAP/skills-flow.md`; adjusted `verify`, `prototype-data`, `prototype-artifact`, `postmortem` cross-references.

## 2026-04-28

> **Note:** The decisions in **Second Upstream Review** and **Deprecation Review** were interim. **2026-04-29** fully mirrored Matt’s active engineering skills and removed deprecated folders from this repo.

### Second Upstream Review (historical)

- Re-checked `mattpocock/skills` at commit `c21cf6ec93b4a25a5118a1a600ebb777e50d6c2e`.
- At that time the repo kept `/domain-model` and marked `grill-with-docs` as a rename candidate; **2026-04-29** replaced that with `grill-with-docs` only.

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

### Deprecation Review (historical)

- These skills were later **removed** from this repo on **2026-04-29** to match Matt:
  - `design-an-interface`
  - `qa`
  - `ubiquitous-language`

### Upstream Candidates

- Identified active upstream skills missing locally at the time (partially resolved **2026-04-29** — `diagnose` and `triage` imported; upstream name is `triage`, not `github-triage`):
  - `write-a-skill`
  - `git-guardrails-claude-code`
  - `migrate-to-shoehorn`
  - `scaffold-exercises`
  - `setup-pre-commit`
- Identified upstream personal skills that should not be imported by default:
  - `edit-article`
  - `obsidian-vault`

### Known Follow-Up (historical)

- Several items below were addressed **2026-04-29** (`diagnose`, `triage`, `MAP` updates, deprecated removal). Remaining optional imports: misc/personal upstream skills.

- ~~Decide whether to import `diagnose` and `write-a-skill` first.~~ (`diagnose` done; `write-a-skill` still optional.)
- ~~Decide whether deprecated local skills should be moved into a `deprecated/` folder or only excluded from sync.~~ (Removed from repo to match Matt.)
- ~~Update `MAP/skills-readme.md` after the active/deprecated split is finalized.~~
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
