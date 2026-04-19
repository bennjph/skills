---
name: prototype-data
description: >
  Generate a structured JSON data model with realistic sample data for a feature or product.
  Separates data modeling from visual rendering — use this first, then optionally invoke
  prototype-artifact to visualize. Use when user says "prototype data", "JSON model",
  "sample data", "data model", or wants to define what the feature IS before rendering it.
  Does not replace a PRD — produces inspectable data artifacts before or alongside specs.
---

# Prototype Data (JSON-first)

Define the feature through structured data before any UI exists. The JSON becomes the shared source of truth — human can edit it, agent can read it, renders can consume it.

This is step 1 of the prototyping pipeline. Step 2 is `prototype-artifact` (optional — you may just want data).

```
prototype-data → [prototype-artifact] → grill-me → to-prd → ...
```

## Where in the workflow

- **After `domain-model` or `grill-me`:** You know what the domain is. Now you model the data.
- **Before `prototype-artifact`:** The artifact skill reads this JSON to render.
- **Standalone:** Sometimes you just want the data model. No visual needed.

**Does not replace PRD.** Written specs (`to-prd`) remain for requirements and decisions.

## Ask every time (before building)

**1. What are you modeling?**

Ask: *What feature or product are we modeling data for?* Let the user describe in their own words. If a domain model (CONTEXT.md) exists, use its terms.

**2. Where should files live?**

Ask explicitly: *Where do you want the JSON data model saved?* Do not pick a path without confirmation.

**3. What artifact types are needed?**

Ask: *What does this feature need?* Pick one or more:

| Type | What it captures | Example |
|------|-----------------|---------|
| **Data model** | Entities, fields, relationships, sample records | Users, orders, products with realistic rows |
| **Flow** | Steps, branches, decisions, parallel paths | User onboarding flow, checkout sequence |
| **Screen layout** | Regions, content blocks, navigation structure | Dashboard with sidebar, main content, action bar |
| **Timing/animation** | States over time, transitions, durations, reveals | Spinning wheel → landing → card reveal (3s, 0.5s, 0.3s) |

User can pick multiple (e.g., "data model + flow + timing").

## Process

### 1. Define the schema

For each artifact type the user picked, produce a JSON structure:

**Data model:**
```json
{
  "type": "data-model",
  "name": "trip-itinerary",
  "entities": {
    "travelers": [
      {
        "id": "t1",
        "firstName": "Sofia",
        "lastName": "Ramirez",
        "avatar": "https://...",
        "travelStyle": "foodie"
      }
    ],
    "itineraryItems": [
      {
        "id": "i1",
        "day": 1,
        "name": "Le Marais Food Tour",
        "startTime": "10:00",
        "duration": "2h",
        "rating": 4.8,
        "reviewCount": 342,
        "tags": ["food", "walking"],
        "photo": "https://...",
        "description": "..."
      }
    ]
  },
  "relationships": [
    { "from": "itineraryItems", "to": "travelers", "type": "has-participants" }
  ]
}
```

**Flow:**
```json
{
  "type": "flow",
  "name": "onboarding",
  "nodes": [
    { "id": "start", "label": "User opens app", "type": "start" },
    { "id": "auth-check", "label": "Authenticated?", "type": "decision" },
    { "id": "login", "label": "Show login screen", "type": "step" },
    { "id": "dashboard", "label": "Show dashboard", "type": "step" }
  ],
  "edges": [
    { "from": "start", "to": "auth-check" },
    { "from": "auth-check", "to": "login", "label": "No" },
    { "from": "auth-check", "to": "dashboard", "label": "Yes" },
    { "from": "login", "to": "dashboard", "label": "Success" }
  ]
}
```

**Screen layout:**
```json
{
  "type": "screen",
  "name": "trip-dashboard",
  "regions": [
    { "id": "header", "role": "navigation", "content": ["trip-title", "date-range", "cover-photo"] },
    { "id": "sidebar", "role": "traveler-list", "content": ["avatars", "names", "travel-styles"] },
    { "id": "main", "role": "itinerary", "content": ["day-tabs", "item-cards", "map-preview"] }
  ]
}
```

**Timing/animation:**
```json
{
  "type": "timing",
  "name": "spin-wheel-reveal",
  "phases": [
    { "id": "idle", "duration": "0s", "state": "wheel visible, button pulsing", "trigger": "user presses spin" },
    { "id": "spinning", "duration": "3s", "state": "wheel rotating, sound playing", "trigger": "timer expires" },
    { "id": "landing", "duration": "0.5s", "state": "wheel decelerating, pointer highlights tip", "trigger": "animation ends" },
    { "id": "reveal", "duration": "0.3s", "state": "card slides up below wheel, tip text visible", "trigger": "none (end state)" }
  ]
}
```

These schemas are **starting points**, not rigid standards. Adapt to the feature's needs. If the feature needs something these shapes don't cover, propose the shape and confirm with the user.

### 2. Fill with realistic sample data

Strong sample data is what makes this skill valuable. Follow these rules:

**Include variation:**
- Short and long text
- Missing optional fields
- Crowded and empty states
- High and low values (ratings, counts)
- Different languages or name lengths where relevant
- Awkward but realistic edge cases

**Do NOT use:**
- Lorem ipsum
- "John Doe" / "Jane Smith" repeated
- Placeholder URLs (`https://example.com/photo`)
- Uniform data (every record same length, same shape)

**Media:** Use real image URLs from Unsplash, Pexels, or similar when possible. If the user has existing assets, reference those. Never hallucinate URLs.

**Quantity:** Enough to stress the design — typically 3-8 records per entity. If one record demonstrates the edge case, that's enough. If you need variety to show layout stress, add more.

### 3. Save and confirm

Write the JSON to the user-specified path. Show a summary of what was produced:
- Which artifact types
- How many entities/records
- Notable edge cases included
- Where the file lives

Ask: *Should anything be added or changed?* Iterate until the user is satisfied.

## Iteration

When the user returns to extend the data model:
1. Read the existing JSON
2. Confirm what's changing (new entities, more records, different edge cases)
3. Update in place
4. The same JSON can then feed `prototype-artifact` for rendering

## Rules

- **Ask, don't assume** — save path every time.
- **Realistic data over clean data** — the point is to stress the design, not look pretty.
- **One JSON file per feature** unless the user asks to split. Keep related artifacts together.
- **Schema is adaptable** — the shapes above are defaults. If the feature needs something different, propose it and confirm.
