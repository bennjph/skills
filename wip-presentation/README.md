# WIP Presentation Skill

This workspace is the shaping area for a new skill focused on creating, editing, and updating `.pptx` presentations with stronger narrative quality and better design taste than generic AI deck generation.

The working premise is simple: the hard part is not placing boxes on slides. The hard part is understanding the decision, shaping the message, sequencing the story, and then expressing that logic through an editable deck that feels deliberate.

## What this workspace is for

- Define what a high-quality presentation skill must actually do.
- Separate narrative work from visual and file-format work.
- Make the `.pptx` pipeline explicit: prototype first, then build, then verify.
- Capture elite deck-design standards as instructions rather than loose inspiration.
- Build enough understanding that a future `SKILL.md` is based on decisions rather than vibes.

## Core principles

- Narrative before layout.
- One slide, one job.
- Prototype the idea before authoring the deck.
- Default to editable output, not screenshot theater.
- Use opinionated quality gates so the result does not drift into AI deck cliches.

## Workstreams

- [technical-crud-pptx.md](/Users/corphr.software/Documents/skills/wip-presentation/workstreams/technical-crud-pptx.md): how an agent should read, create, update, delete, and verify PPTX safely.
- [prototype-json-pipeline.md](/Users/corphr.software/Documents/skills/wip-presentation/workstreams/prototype-json-pipeline.md): how `prototype-data` and `prototype-artifact` should front-run deck creation.
- [design-process.md](/Users/corphr.software/Documents/skills/wip-presentation/workstreams/design-process.md): elite designer process, taste rules, and quality signals.
- [writing-style-guidelines.md](/Users/corphr.software/Documents/skills/wip-presentation/workstreams/writing-style-guidelines.md): crisp communication rules adapted from the rewrite workflow.
- [narrative-architecture.md](/Users/corphr.software/Documents/skills/wip-presentation/workstreams/narrative-architecture.md): message logic, audience fit, and business-story sequencing.

## Working artifacts

- [presentation-skill-model.json](/Users/corphr.software/Documents/skills/wip-presentation/models/presentation-skill-model.json): JSON-first source model of the skill surface, use cases, workflow, and gates.
- [presentation-skill-map.html](/Users/corphr.software/Documents/skills/wip-presentation/artifacts/presentation-skill-map.html): rendered visual map of the current model.
- [elite-presentation-engineering-synthesis.md](/Users/corphr.software/Documents/skills/wip-presentation/research/elite-presentation-engineering-synthesis.md): compressed working synthesis of the research note.
- [AI-CRAFT-TRANSFER-INSIGHTS.md](/Users/corphr.software/Documents/skills/wip-presentation/research/AI-CRAFT-TRANSFER-INSIGHTS.md): what transfers from the `ai-craft` UI-generation operating model into presentations.
- [PRESENTATION-GENERATION-HYPOTHESIS.md](/Users/corphr.software/Documents/skills/wip-presentation/research/PRESENTATION-GENERATION-HYPOTHESIS.md): first hypothesis for presentation-training priors, dense shortcuts, and likely default failure modes.
- [PRESENTATION-OPERATING-STACK.md](/Users/corphr.software/Documents/skills/wip-presentation/product/PRESENTATION-OPERATING-STACK.md): presentation-specific operating stack for generation and maintenance.
- [PRESENTATION-EVALUATION-SYSTEM.md](/Users/corphr.software/Documents/skills/wip-presentation/product/PRESENTATION-EVALUATION-SYSTEM.md): scoring rubric and failure library for deck quality and update resilience.
- [PRESENTATION-VOCABULARY-PACKAGE.md](/Users/corphr.software/Documents/skills/wip-presentation/product/PRESENTATION-VOCABULARY-PACKAGE.md): closed vocabulary package for narrative, slide types, title rules, and banned patterns.
- [DECK-BRIEF-TEMPLATE.md](/Users/corphr.software/Documents/skills/wip-presentation/templates/DECK-BRIEF-TEMPLATE.md): template for defining the job before generation.
- [SLIDE-CONTRACT-TEMPLATE.md](/Users/corphr.software/Documents/skills/wip-presentation/templates/SLIDE-CONTRACT-TEMPLATE.md): template for standardizing important slide roles before rendering.
- [SEQUENCE.md](/Users/corphr.software/Documents/skills/wip-presentation/SEQUENCE.md): branch order for research and review.
- [PRIORITIZATION-FRAME.md](/Users/corphr.software/Documents/skills/wip-presentation/PRIORITIZATION-FRAME.md): how we will classify what matters, what does not, what prompts can solve, and what needs deeper capability.
- [repo-map.md](/Users/corphr.software/Documents/skills/wip-presentation/repo-map.md): file-by-file structure and contribution map.
- [CHANGELOG.md](/Users/corphr.software/Documents/skills/wip-presentation/CHANGELOG.md): chronological record of workspace changes.
- [WEB.md](/Users/corphr.software/Documents/skills/wip-presentation/WEB.md): mermaid-based visual map of files, pillars, and contributions.
- [01-narrative-review.md](/Users/corphr.software/Documents/skills/wip-presentation/reviews/01-narrative-review.md): first branch review using the prioritization frame.

## Current shape

This is intentionally a WIP workspace, not a finalized skill. The current workspace is organized to let us iterate in three loops:

1. Tighten the standards.
2. Review each branch in sequence and let you prioritize the important parts.
3. Only after that, convert the stable parts into a production-ready skill.

## Immediate next questions

- Which presentation job types deserve first-class workflows?
- How much should the skill enforce narrative gates before opening PowerPoint tooling?
- What is the right default authoring engine for this environment?
- What verification bar distinguishes a professional editable deck from an attractive fake?

## Research-first workflow

We are not drafting the skill yet.

The workflow from here is:

1. Research one branch at a time.
2. Do sense-making for that branch.
3. Separate prompt-solvable problems from deeper capability gaps.
4. Mark what matters, what does not, and what should wait.
5. Let you prioritize before we turn any of it into operating instructions.
