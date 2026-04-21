# Repo Map

This file tracks how the `wip-presentation/` workspace is organized, what each file does, and how it contributes to the main goal:

Build a research-backed path toward a high-quality presentation skill for creating, editing, and updating `.pptx` decks with strong narrative, clear writing, deliberate design, prototype-first planning, and safe technical execution.

## Pillars

The workspace is organized around five main pillars:

1. Narrative
2. Writing
3. Design
4. Prototype-first workflow
5. Technical PPTX CRUD

There is also a sixth support layer:

6. Workspace governance and synthesis

This support layer keeps the research process navigable, reviewable, and updateable over time.

## File Map

### Root coordination files

#### [README.md](/Users/corphr.software/Documents/skills/wip-presentation/README.md)

Purpose:
- front door to the workspace
- explains the goal, principles, workstreams, and current operating mode

Contributes:
- governance
- orientation
- links to source material and review artifacts

#### [SEQUENCE.md](/Users/corphr.software/Documents/skills/wip-presentation/SEQUENCE.md)

Purpose:
- defines the order of branch research
- prevents premature synthesis

Contributes:
- governance
- prioritization flow

#### [PRIORITIZATION-FRAME.md](/Users/corphr.software/Documents/skills/wip-presentation/PRIORITIZATION-FRAME.md)

Purpose:
- defines the classification buckets for each branch review
- separates prompt-solvable problems from deeper capability gaps

Contributes:
- governance
- prioritization
- decision quality

#### [repo-map.md](/Users/corphr.software/Documents/skills/wip-presentation/repo-map.md)

Purpose:
- documents the full file layout and file-to-pillar relationships

Contributes:
- navigation
- change tracking context

#### [CHANGELOG.md](/Users/corphr.software/Documents/skills/wip-presentation/CHANGELOG.md)

Purpose:
- chronological record of what was added, changed, removed, and why

Contributes:
- continuity
- project memory

#### [WEB.md](/Users/corphr.software/Documents/skills/wip-presentation/WEB.md)

Purpose:
- visual map of how files relate to pillars and to each other

Contributes:
- visual navigation
- ongoing sense-making

### Research synthesis

#### [research/elite-presentation-engineering-synthesis.md](/Users/corphr.software/Documents/skills/wip-presentation/research/elite-presentation-engineering-synthesis.md)

Purpose:
- compressed synthesis of the long elite deck engineering research note

Contributes:
- all pillars, especially narrative, design, and technical standards
- shared source material for future branch reviews

#### [research/AI-CRAFT-TRANSFER-INSIGHTS.md](/Users/corphr.software/Documents/skills/wip-presentation/research/AI-CRAFT-TRANSFER-INSIGHTS.md)

Purpose:
- translates the `ai-craft` module into presentation-specific implications

Contributes:
- cross-pillar methodology
- transfer of operating-stack, negative-constraint, and evaluation ideas
- explicit bridge from UI/UX generation research into presentation generation

#### [research/PRESENTATION-GENERATION-HYPOTHESIS.md](/Users/corphr.software/Documents/skills/wip-presentation/research/PRESENTATION-GENERATION-HYPOTHESIS.md)

Purpose:
- frames a first hypothesis for how AI models likely represent and default presentation output

Contributes:
- training-data-median hypothesis for decks
- likely presentation dense shortcuts
- prompt-solvable vs capability-needed split

### Workstream source files

These are branch source notes. They are not the final decisions. They are the current working material for each pillar.

#### [workstreams/narrative-architecture.md](/Users/corphr.software/Documents/skills/wip-presentation/workstreams/narrative-architecture.md)

Primary pillar:
- Narrative

Contributes:
- decision framing
- story spine
- slide-role logic
- audience-specific narrative differences

#### [workstreams/writing-style-guidelines.md](/Users/corphr.software/Documents/skills/wip-presentation/workstreams/writing-style-guidelines.md)

Primary pillar:
- Writing

Contributes:
- action-title rules
- body-copy rules
- speaker-note rules
- compression and tone guidance

#### [workstreams/design-process.md](/Users/corphr.software/Documents/skills/wip-presentation/workstreams/design-process.md)

Primary pillar:
- Design

Contributes:
- elite designer process
- taste rules
- anti-slop constraints
- layout and hierarchy heuristics

#### [workstreams/prototype-json-pipeline.md](/Users/corphr.software/Documents/skills/wip-presentation/workstreams/prototype-json-pipeline.md)

Primary pillar:
- Prototype-first workflow

Contributes:
- JSON-first planning model
- artifact-before-PPTX workflow
- what to model before deck creation

#### [workstreams/technical-crud-pptx.md](/Users/corphr.software/Documents/skills/wip-presentation/workstreams/technical-crud-pptx.md)

Primary pillar:
- Technical PPTX CRUD

Contributes:
- create/read/update/delete/verify model
- runtime and OOXML lane distinctions
- quality gates for editable deck integrity

### Models and visual artifacts

#### [models/presentation-skill-model.json](/Users/corphr.software/Documents/skills/wip-presentation/models/presentation-skill-model.json)

Purpose:
- source-of-truth structured model of use cases, workstreams, quality gates, deliverables, and workflow

Contributes:
- cross-pillar alignment
- future prototype and review tooling
- structured basis for visual artifacts

#### [artifacts/presentation-skill-map.html](/Users/corphr.software/Documents/skills/wip-presentation/artifacts/presentation-skill-map.html)

Purpose:
- rendered visual map of the current skill model

Contributes:
- visual overview
- fast inspection of the current concept shape

### Product and operating-system drafts

These files adapt the `ai-craft` product framing into presentation-specific operating documents.

#### [product/PRESENTATION-OPERATING-STACK.md](/Users/corphr.software/Documents/skills/wip-presentation/product/PRESENTATION-OPERATING-STACK.md)

Primary pillars:
- Narrative
- Prototype-first workflow
- Technical PPTX CRUD
- Governance

Contributes:
- layered operating model for generation and maintenance
- clarifies where prompting belongs
- defines what should be standardized versus project-specific

#### [product/PRESENTATION-EVALUATION-SYSTEM.md](/Users/corphr.software/Documents/skills/wip-presentation/product/PRESENTATION-EVALUATION-SYSTEM.md)

Primary pillars:
- Narrative
- Writing
- Design
- Technical PPTX CRUD

Contributes:
- scoring rubric for deck quality
- failure-mode library for diagnosis
- maintenance-oriented quality gates

#### [product/PRESENTATION-VOCABULARY-PACKAGE.md](/Users/corphr.software/Documents/skills/wip-presentation/product/PRESENTATION-VOCABULARY-PACKAGE.md)

Primary pillars:
- Narrative
- Writing
- Design
- Prototype-first workflow

Contributes:
- closed presentation vocabulary
- narrative and visual decision package
- banned-pattern and title-policy layer for prompting

### Templates

These files define the minimum structured inputs for better generation and maintenance.

#### [templates/DECK-BRIEF-TEMPLATE.md](/Users/corphr.software/Documents/skills/wip-presentation/templates/DECK-BRIEF-TEMPLATE.md)

Primary pillars:
- Narrative
- Writing
- Prototype-first workflow

Contributes:
- structured intake for deck jobs
- clearer audience and decision capture
- reduces generic prompt drift

#### [templates/SLIDE-CONTRACT-TEMPLATE.md](/Users/corphr.software/Documents/skills/wip-presentation/templates/SLIDE-CONTRACT-TEMPLATE.md)

Primary pillars:
- Narrative
- Writing
- Design
- Technical PPTX CRUD

Contributes:
- reusable slide-role specification
- explicit claim-evidence-layout contract
- better update and review stability

### Branch reviews

These files are where the real prioritization work happens. They convert branch notes into "what matters vs what does not."

#### [reviews/01-narrative-review.md](/Users/corphr.software/Documents/skills/wip-presentation/reviews/01-narrative-review.md)

Primary pillar:
- Narrative

Contributes:
- first explicit prioritization pass
- generic AI limitation analysis
- prompt-solvable vs capability-needed separation
- open decisions for your review

## How the files connect

### Source layer

- `research/elite-presentation-engineering-synthesis.md`
- `workstreams/*.md`

These files gather raw and semi-structured thinking.

### Review layer

- `SEQUENCE.md`
- `PRIORITIZATION-FRAME.md`
- `reviews/*.md`

These files turn source material into prioritizable judgments.

### Model layer

- `models/presentation-skill-model.json`

This turns the emerging understanding into structured data.

### Artifact layer

- `artifacts/presentation-skill-map.html`
- `WEB.md`

These files make the workspace inspectable visually.

### Operating-system layer

- `product/PRESENTATION-OPERATING-STACK.md`
- `product/PRESENTATION-EVALUATION-SYSTEM.md`
- `product/PRESENTATION-VOCABULARY-PACKAGE.md`

These files start turning research into reusable operating methods without jumping prematurely to a final skill.

### Template layer

- `templates/DECK-BRIEF-TEMPLATE.md`
- `templates/SLIDE-CONTRACT-TEMPLATE.md`

These files define the structured inputs that should exist before prompting or PPTX work begins.

### Governance layer

- `README.md`
- `repo-map.md`
- `CHANGELOG.md`

These files keep the project navigable and maintain continuity as more files are added.

## Update rules

Whenever a meaningful file is added, changed, or removed in this workspace:

1. Update `CHANGELOG.md`
2. Update `repo-map.md` if the file changes the workspace structure or role map
3. Update `WEB.md` if the file adds a new branch, review, model, artifact, or governance connection

## Current gaps

The following branch reviews do not exist yet and should be added over time:

- writing review
- design review
- prototype workflow review
- technical CRUD review

These should be created in `reviews/` as the next sequential steps.
