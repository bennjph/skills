# Skill Sync TODO

## Scope

- Source of truth: this repo's top-level skill folders.
- Install targets:
  - Codex global skills: `~/.codex/skills/`
  - Cursor global skills: `~/.cursor/skills/`
- Excluded from sync: `wip-presentation/` because the presentation/PPT generation work is still WIP.
- Preserve installed global skills that are not present in this repo.

## Execution Checklist

- [x] Inventory repo skill folders and installed Codex/Cursor skill folders.
- [x] Create timestamped backup snapshots of current Codex and Cursor global skill folders.
- [x] Sync all non-WIP repo skill folders into Codex global skills.
- [x] Sync all non-WIP repo skill folders into Cursor global skills.
- [x] Update repo documentation so it describes both Codex and Cursor install targets.
- [x] Add `familiar` to the documented skill inventory.
- [x] Keep presentation/PPT generation material documented as excluded/WIP.
- [x] Verify every non-WIP repo skill folder exists in both global install targets.
- [x] Verify synced folders match repo source.
- [x] Verify unrelated global skills remain present.
- [x] Review git status and summarize changed files.

## Result

- Synced non-WIP repo skills into both global install targets.
- Added `familiar` as a new installed skill for both Codex and Cursor.
- Left `wip-presentation/` repo-local because presentation/PPT generation is still WIP.
- Created a local backup snapshot under `.skill-sync-backups/`.
- Added `.gitignore` rules for `.DS_Store` and local sync backups.

## 2026-04-29 — Matt mirror sync

- Mirrored Matt engineering skills at `f71bb975bfae2dc0d31c529c7dd4a8479ecc3748`: added **`grill-with-docs`**, **`diagnose`**, **`triage`**, **`setup-matt-pocock-skills`**; removed **`grill-me`**, **`domain-model`**, **`design-an-interface`**, **`qa`**, **`ubiquitous-language`**.
- Re-ran rsync from this repo into `~/.codex/skills/` and `~/.cursor/skills/` for every top-level skill folder that contains `SKILL.md` (excluding `wip-presentation/` and `MAP/`).
- Push `github.com/bennjph/skills` when satisfied with the commit.

## Self-Verification Commands

```sh
find . -maxdepth 2 -name SKILL.md -print
find ~/.codex/skills ~/.cursor/skills -maxdepth 2 -name SKILL.md -print
for d in */SKILL.md; do name=${d%/SKILL.md}; [ "$name" = wip-presentation ] && continue; diff -qr "$name" "$HOME/.codex/skills/$name"; diff -qr "$name" "$HOME/.cursor/skills/$name"; done
git status --short
```
