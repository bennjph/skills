---
name: prototype-artifact
description: >
  Generate visual artifacts (flowcharts, screen mockups, timing diagrams) from a JSON
  data model. Step 2 of the prototyping pipeline — reads JSON produced by prototype-data.
  Use when user says "render prototype", "visualize this", "show me the flow",
  "generate mockup", or wants to turn data into something inspectable.
  Does not replace a PRD — produces visual references the PRD can point to.
---

# Prototype Artifact (Visual from JSON)

Take a structured JSON data model and render it as a visual artifact the human can inspect, edit, and iterate on. Reads JSON from `prototype-data` (or any JSON the user points to).

This is step 2 of the prototyping pipeline. Step 1 is `prototype-data` (JSON creation).

```
prototype-data → prototype-artifact → grill-me → to-prd → ...
```

## Where in the workflow

- **After `prototype-data`:** You have the JSON. Now render it.
- **Standalone:** User already has JSON data and just wants it visualized.
- **Before or during `grill-me`:** Visual artifact drives sharper grilling.
- **Alongside `to-prd`:** PRD references the visual artifact as a specification aid.

**Does not replace PRD.** Written specs (`to-prd`) remain for requirements and decisions.

## Ask every time (before building)

**1. Which JSON to render?**

Ask: *Which JSON file should I render?* If the user just ran `prototype-data`, it's the file they saved. If not, confirm the path. Read it before proceeding.

**2. What to render from it?**

Determine from the JSON's `type` field (or ask if ambiguous):

| JSON type | Visual output |
|-----------|--------------|
| `data-model` | Entity relationship diagram, sample record cards, field breakdown |
| `flow` | Flowchart with nodes, edges, branches, labels |
| `screen` | Layout mockup with regions, content blocks, navigation |
| `timing` | Timeline/phases diagram with durations, states, triggers |

If the JSON contains multiple types, confirm which to render (or render all as separate sections).

**3. Where should the visual artifact live?**

Ask explicitly: *Where do you want the rendered artifact saved?*

**4. Which render target?**

| Option | What it means |
|--------|----------------|
| **Canvas** | Cursor Canvas: `.canvas.tsx` beside chat (IDE-managed path, `cursor/canvas` SDK, data embedded — see Canvas skill constraints) |
| **HTML** | Standalone file(s) you open in a browser; full freedom for layout, fetch, custom JS |
| **React app in `code/`** | A small app under the repo's code root — good when the prototype should grow toward real product |
| **Custom JSON renderer** | User already has an app/tool that reads JSON — agent confirms the JSON matches the renderer's expected shape |

## Process

### 1. Read and parse the JSON

Read the specified JSON file. Identify:
- Artifact type(s) present
- Entities and their fields
- Relationships and cardinality
- Sample records and their variation
- Any embedded comments or instructions

### 2. Map JSON to visual structure

For each artifact type:

**Data model → ER diagram or record cards:**
- Show entities as cards/blocks
- Show relationships as labeled connections
- Show sample data inline or in expandable sections
- Highlight edge cases visually (long text, missing fields, crowded states)

**Flow → Flowchart:**
- Render nodes as boxes (steps) or diamonds (decisions)
- Render edges as arrows with labels
- Show start/end clearly
- Lay out left-to-right or top-to-bottom, grouping parallel paths

**Screen → Layout mockup:**
- Render regions as labeled blocks with proportional sizing
- Show content placeholders inside regions
- Indicate navigation elements (tabs, buttons, links)
- Use the sample data to populate placeholders where possible

**Timing → Phase diagram:**
- Render phases as a horizontal timeline
- Show duration labels
- Show state descriptions per phase
- Show triggers as arrows between phases
- Annotate with the animation/transition behavior

### 3. Produce the artifact

**Canvas:** Write/update per Canvas skill rules. Embed the JSON snapshot inline (Canvas cannot `fetch` from repo files). Use `cursor/canvas` components only. The canvas is a preview — the canonical JSON lives in the repo, not in the canvas.

**HTML:** Write standalone file(s) at the user-specified path. Can embed JSON inline or load it via `<script src>` if co-located. Full control over layout, styling, and interactivity.

**React app:** Scaffold or update under the user-specified path in `code/`. Follow existing project conventions if any. The app should read from the JSON file at a known relative path.

**Custom renderer:** Confirm the JSON shape matches what the renderer expects. If there's a mismatch, adjust the JSON (with user permission) or note the gap. Do not pretend a renderer exists if it doesn't.

### 4. Save and confirm

Write the visual artifact to the confirmed path. Show:
- Where the file lives
- How to open it (browser URL, Canvas click, dev server command)
- What was rendered (which artifact types, how many entities/flows/screens)
- Any limitations (e.g., "Canvas shows a snapshot — edit the JSON to update")

Ask: *Does this match what you expected? Anything to adjust?*

## Iteration

When the user wants changes:
1. **Edit the JSON** — the canonical source. Then re-render.
2. **Edit the visual directly** — if the user modifies the HTML/React, the agent reads the changes and can update the JSON to match.
3. **Re-render** — if the JSON changed but the visual didn't update yet, re-run the render step.

The golden rule: **JSON is the source of truth.** If JSON and visual diverge, JSON wins. Resolve by re-rendering or by updating JSON to match deliberate visual edits.

## Rules

- **Ask, don't assume** — JSON path, save path, and render target every time.
- **JSON is canonical** — the visual is a derived artifact. Edit JSON to iterate.
- **Canvas constraints are real** — if the user wants live JSON loading, Canvas can't do it. Use HTML or React instead. Say so.
- **Keep renders proportional** — the goal is an inspectable loop, not production polish.
- **No pretending** — if a renderer doesn't exist, say so. Don't generate code that references nonexistent tools.
