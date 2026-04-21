# Presentation Generation Hypothesis

This note adapts the `ai-craft` hypothesis model to elite presentation creation, editing, and maintenance.

Some parts below are evidence-backed by adjacent AI-craft research.

Some parts are informed inference about presentation generation specifically.

Where a point is inferred rather than directly proven, it should be treated as a working hypothesis to validate later.

## Core hypothesis

Generic AI deck output tends toward the statistical median of public slide culture.

That median is shaped less by elite presentation craft and more by:

- public slide templates
- generic pitch-deck examples
- business blog posts about presentations
- template marketplaces
- corporate communication norms visible on the open web
- image-caption or screenshot pairs that overrepresent surface appearance rather than narrative quality

The result is output that often looks presentation-like without being strategically strong.

## Working assumptions about training-data priors

These are reasoned hypotheses, not confirmed internals.

### Likely source layers

1. Public web pages discussing presentations
2. Download pages and previews for PowerPoint or Google Slides templates
3. Public pitch deck examples and startup storytelling content
4. Office-product tutorials and how-to material
5. Screenshots or thumbnails of slide decks
6. Documents and PDFs where slide-like structures are present
7. Code and markup for presentation frameworks, slide libraries, and dashboards

### Likely label channels

The model may not have rich "slide quality" labels.

It likely infers slide meaning from:

- surrounding text on web pages
- file names like `pitch-deck`, `investor-update`, `quarterly-business-review`
- OCR-able title text within slides
- repeated layout patterns
- common phrases such as `agenda`, `our solution`, `market opportunity`, `thank you`

That means the model may learn strong correlations for slide form without learning strong standards for narrative quality.

## Hypothesis: what the presentation median looks like

The median AI deck likely overproduces these patterns:

- topic-title slides instead of claim-title slides
- bullet stacks that summarize but do not argue
- three-column comparison slides
- section-divider or agenda filler
- weak proof hierarchy
- broad, pleasant visual systems with little point of view
- charts that look presentable but do not carry a sharp takeaway
- too many slides because expansion is easier than subtraction

## Hypothesis: why elite deck work is underrepresented

The best presentation work is probably less represented in public training corpora because:

- many elite decks are private
- board, fundraising, and strategy decks are often confidential
- the value is in internal logic, not just visible styling
- annotations, presenter behavior, and narrative sequencing are not richly labeled
- slide images alone do not expose what made the deck persuasive

This suggests a key constraint:

The model may have broad exposure to presentation surfaces, but limited exposure to top-tier narrative reasoning inside high-stakes decks.

## Dense shortcuts for presentation prompting

These should be treated as candidates to test, not yet as validated defaults.

### Narrative shortcuts

- `McKinsey-style action titles`
- `board-decision narrative`
- `one-message-per-slide`
- `executive skim-first structure`
- `appendix-ready evidence trail`
- `Duarte tension to resolution`

### Design shortcuts

- `Swiss editorial grid`
- `consulting-grade chart discipline`
- `bento-style information compartments`
- `flush-left hierarchy`
- `native chart, not handmade chart`
- `speaker-notes-aware deck`

### Technical shortcuts

- `Slide Master discipline`
- `editable native PPTX objects`
- `Selection Pane semantic naming`
- `theme-safe update path`
- `OOXML-aware verification`

## Negative constraints for presentation generation

These likely matter as much as positive instructions:

- no topic-only titles
- no agenda slide by default
- no three-box slide by default
- no icon row filler
- no stock-photo cliche imagery
- no generic startup gradient unless explicitly wanted
- no card wall unless the information architecture demands it
- no decorative chart without a stated takeaway
- no bullet pile that could be a memo paragraph instead

## What prompts can likely solve

- capturing audience and decision first
- forcing action-title discipline
- requiring slide roles
- requiring cut candidates
- banning common generic patterns
- requiring main-story versus appendix separation
- demanding one message per slide

## What prompts alone probably cannot solve

- reliable cross-slide consistency
- good update behavior on existing `.pptx` files
- native chart integrity checks
- reading-order and accessibility verification
- precise template and theme-safe maintenance
- semantic object targeting for repeated edits
- trustworthy evaluation of whether the story truly persuades the intended audience

## Implication for the future skill

The skill should not be designed as a better prompt.

It should be designed as a presentation operating system with layers:

1. narrative thesis
2. reality model
3. visual and structural plan
4. presentation vocabulary package
5. slide contracts
6. PPTX generation and update surface
7. verification and maintenance loop

## Validation questions

These hypotheses still need testing:

1. Which presentation shortcuts actually improve deck quality consistently?
2. Which shortcuts are universal versus job-type specific?
3. What does median output look like across models and tools for the same deck brief?
4. Which failure modes are mostly prompt issues, and which are structural system issues?
