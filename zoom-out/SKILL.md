---
name: zoom-out
description: >
  Zoom out to a higher level of abstraction and map the surrounding code context.
  Use when user says "zoom out", "big picture", "where does this fit", "show me the map",
  "how do these connect", or needs to understand how a code area fits into the broader system.
---

Go up a layer of abstraction. Map the surrounding context.

## Process

1. Identify what module/file the user is currently in or asking about
2. Go up one level — what calls this, what does this call, what does it depend on
3. Produce a structured map

## Output format

```
## [Module/Area Name]

**Purpose:** One sentence.

### Inbound (what calls this)
- `path/to/caller.ts` — calls [exported function/component]
- `path/to/other.ts` — imports [X]

### Outbound (what this calls)
- `path/to/dep.ts` — provides [Y]
- `path/to/service.ts` — sends [Z]

### Siblings (same layer)
- `path/to/sibling.ts` — [what it does]

### Key data flow
[2-3 sentence description of how data moves through this area]
```

If the area is small enough that a single-level map captures everything, stop. If it's part of a larger system, note what's above and below without expanding into those layers.

## Scope

Only map the immediately surrounding layer. One level up, one level down. The user asked to zoom out, not to document the entire codebase.
