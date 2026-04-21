# Technical: PPTX CRUD

This workstream defines how an LLM should safely create, read, update, delete, and verify `.pptx` files.

## Working stance

The skill should treat PowerPoint as a structured document system with three layers:

1. Narrative and slide plan
2. Presentation object model
3. Underlying OOXML package

Good output comes from keeping those layers aligned instead of jumping straight to pixels.

## CRUD model

### Create

- Start from a structured deck plan, not direct canvas improvisation.
- Build with reusable layout primitives: title blocks, section openers, evidence slides, comparison slides, appendix slides.
- Prefer editable text, tables, charts, and notes over rasterized text.
- Bind slide creation to a declared theme, slide-size choice, and layout system.

### Read

- Extract deck metadata: title, slide count, notes, layouts, theme, media inventory.
- Extract semantic content: slide titles, body copy, chart data, table text, speaker notes, hyperlinks.
- Detect structural risks: duplicate titles, hidden overflow, image-only slides, broken relationships, missing media.
- Read both the rendered experience and the underlying object structure when diagnosing edits.

### Update

- Target updates at slide roles, placeholders, or stable object identities where possible.
- Distinguish content edits from layout edits from theme edits.
- Preserve master-layout intent; do not brute-force per-slide overrides unless necessary.
- Support common update classes: rewrite copy, swap data, replace images, restyle template, reorder slides, expand appendix, patch speaker notes.

### Delete

- Allow safe deletion of slides, objects, notes, and unused assets.
- Clean up package relationships so deleted content does not leave broken references.
- Detect accidental narrative breakage when removing slides from the middle of an argument.

### Verify

- Render the deck or slide previews.
- Inspect the PPTX package for expected parts and obvious corruption.
- Confirm editable text is still present as text.
- Confirm charts remain native where charts are expected.
- Check slide order, title logic, contrast, and file-size sanity.

## Recommended implementation lanes

### Lane A: environment-native authoring

For this Codex environment, the strongest default authoring path is the existing PowerPoint runtime based on `@oai/artifact-tool`. It supports import/export, editable objects, preview rendering, and native charts. That makes it the best default lane for final deck creation and revision here.

### Lane B: OOXML inspection and surgical patching

Use the `.pptx` package as a ZIP of XML parts when you need precision beyond the normal authoring surface:

- inspect relationships
- audit theme/layout structure
- detect missing parts or broken media
- make targeted changes that the higher-level API cannot express cleanly

This is the precision lane, not the default authoring lane.

### Lane C: comparative library awareness

The wider ecosystem includes libraries like PptxGenJS and python-pptx. They are useful reference points for what a general presentation skill might need to support across environments, but they should not dictate the default implementation in this Codex setup.

## Hard problems the skill must model explicitly

- Object identity across edits
- Mapping narrative roles to physical slides
- Theme-safe updates without local formatting sprawl
- Chart updates without breaking native chart semantics
- Importing existing decks that were not cleanly authored
- Avoiding screenshot-only output that looks correct but cannot be maintained

## Quality gates

- No image-only final slides when editable text is required.
- No silent overflow or off-canvas content.
- No orphaned media or broken relationship parts.
- No update path that depends on manual hunting across every slide.
- No final deck that passes visually but fails structurally.

## Practical skill requirements

- The skill should be able to explain what kind of edit it is about to perform.
- The skill should maintain a stable slide inventory and role map.
- The skill should verify after edits, not just after initial creation.
- The skill should know when to escalate from normal authoring to OOXML inspection.
