# Presentation Capability System

This workspace defines a single presentation capability system for creating, updating, and verifying professional `.pptx` decks. It exists to turn research, hypotheses, and operating decisions into a durable system that can later ship as one presentation orchestrator.

## Language

**Presentation Capability System**:
The single domain incubated in this repo for presentation creation, editing, maintenance, and quality control across multiple presentation situations.
_Avoid_: multiple products, shared skills repo, deck factory

**Presentation Orchestrator**:
The top-level skill or entry point that runs the presentation workflow end to end.
_Avoid_: monolithic prompt, manual skill bundle

**Work Phase**:
A named phase of work the Presentation Orchestrator moves through while shaping, building, adapting, or verifying a deck.
_Avoid_: stage, deck stage, ad hoc step

**Use-Case Family**:
A recurring presentation situation with distinct audience, stakes, and evidence patterns inside the same system.
_Avoid_: separate product, vertical

**Audience**:
The specific people the deck is trying to move, such as internal colleagues, vendors, customers, executives, or investors.
_Avoid_: visual style, market category

**Organization Posture**:
The cultural and stylistic expectations of the organization or brand context the deck must feel native to.
_Avoid_: audience, communication job, brand template only

**Deck Archetype**:
A reusable presentation mode that pre-decides density, proof style, pacing, appendix depth, and visual posture for a class of presentation jobs.
_Avoid_: one-off style invention, generic template only

**Deck Archetype Comparison**:
The practice of presenting multiple plausible Deck Archetypes side by side so the operator can scrutinize fit and expose missing archetypes.
_Avoid_: hidden classification, forced single choice too early, unqualified archetype comparison

**Style Pool**:
A curated reusable library of visual systems available for selection and adaptation across deck jobs.
_Avoid_: one-off style generation, random template pile

**Style System**:
A reusable visual execution system covering typography, grids, theme, spacing, chart treatment, and motion posture.
_Avoid_: deck archetype, template screenshot, mood board only

**Style Variant**:
A job-specific personalization of a selected Style System for a particular organization posture, communication job, or deck.
_Avoid_: brand-new style invention, manual per-slide override set

**Style Fit Tags**:
Metadata on a Style System that indicates which organization postures, deck archetypes, or presentation situations it fits best.
_Avoid_: hard partitioning, implied universal fit

**Incubation Mode**:
The current R&D phase where the system stays more exploratory so categories, workflows, and gaps can be discovered before the production skill is tightened.
_Avoid_: final production behavior, frozen operating model

**Communication Job**:
The change in understanding, belief, or decision the deck is meant to create in its audience.
_Avoid_: slide request, content dump

**Presenter Voice**:
The characteristic way the presenter should sound across titles, on-slide copy, and speaker notes.
_Avoid_: audience, organization posture, visual style

**Voice Profile**:
A reusable tone and expression profile that defines how a presenter typically sounds across presentation work.
_Avoid_: one-off tone invention, visual style

**Voice Variant**:
A light job-specific tuning of a selected Voice Profile for a particular presentation context.
_Avoid_: full rewrite of presenter identity, ad hoc tone drift

**Visual Posture**:
The chosen visual character of the deck, including simplicity, polish, density, and restraint, independent of whether the audience is internal or external.
_Avoid_: audience type, market segment

**Taste Standard**:
The cross-cutting expectation that decks should feel deliberate, clean, modern, and high-signal rather than stale, cluttered, or generic.
_Avoid_: optional polish, decoration layer

**Prototype JSON**:
The structured planning source of truth that captures the communication job, audience, narrative, evidence, and slide plan before deck creation.
_Avoid_: final deliverable, raw prose blob

**Prototype Artifact**:
An inspectable visual rendering of the Prototype JSON used to review options, sequence, density, and story before deck creation.
_Avoid_: final deck, polished deliverable

**Prototype Tree**:
A progressive branching approach to prototyping where early rounds compare a few distinct directions and later rounds go deeper on the selected direction.
_Avoid_: flat style dump, full polish on every option, one-shot visual choice

**Slide Plan**:
The ordered definition of slide roles, titles, evidence, and visual intent that the deck build consumes.
_Avoid_: rough outline, ad hoc slide list

**Slide Role**:
A named job a slide performs in the deck, such as context, proof, comparison, recommendation, or appendix evidence.
_Avoid_: arbitrary slide label, per-archetype invention

**Slide Contract**:
A structured definition of what a slide type must do, show, and preserve before rendering or update work begins.
_Avoid_: loose prompt fragment, layout guess

**Slide Contract Variant**:
An archetype-specific adaptation of a base Slide Contract for when the same slide role needs different proof, density, or layout behavior.
_Avoid_: entirely separate contract universe, per-deck reinvention

**Existing Deck Adaptation**:
Updating a provided deck while preserving or deliberately reshaping its narrative, structure, and editability rather than patching slide surfaces blindly.
_Avoid_: direct slide surgery, cosmetic-only revision

**Deck Rehydration**:
The process of reconstructing missing upstream context such as communication job, audience, archetype, slide roles, and evidence map before adapting an existing deck.
_Avoid_: blind patching, context-free editing

**Rehydration Package**:
The minimum recovered context required before an existing deck can be safely adapted.
_Avoid_: partial guesswork, implied understanding

**PPTX Build Gate**:
The explicit approval point after prototype review where the system is allowed to create or update the final editable PowerPoint deck.
_Avoid_: default behavior, automatic generation

**Deck**:
The editable presentation artifact produced or updated for a specific communication job.
_Avoid_: PowerPoint as the domain name, generic file

**Human-in-the-Loop Collaboration**:
The default operating mode where the system works with a human through key judgment steps instead of treating the deck as a one-shot autonomous generation task.
_Avoid_: one-shot generation, fire-and-forget automation

**Decision Surfacing**:
The rule that major system choices are shown explicitly to the human instead of being silently collapsed by the orchestrator.
_Avoid_: hidden automation, silent major decisions

**System-Shaping Decision**:
A choice that changes the presentation system itself rather than only affecting one deck run.
_Avoid_: tiny judgment call, one-off deck tweak

**Decision Artifact**:
A durable repo artifact that records a System-Shaping Decision when future work would otherwise lose the reasoning.
_Avoid_: transient chat only, file for every tiny choice

**ADR**:
A narrowly used decision record for a hard-to-reverse, surprising tradeoff that future readers would otherwise re-litigate.
_Avoid_: default note format, record for every system choice

**Scaled Operating Model**:
The richer repo operating shape used when durable memory, layered docs, and multi-workstream coordination are core to the work.
_Avoid_: thin scaffold, minimal handoff only

**Operating Layer**:
The repo-operating files added around the existing brownfield content to provide live pointers, durable memory, and coordination surfaces.
_Avoid_: full repo reorganization, duplicate document lanes

**Brownfield Preservation**:
The rule that the current research and product structure should stay in place while the Operating Layer is added around it.
_Avoid_: needless renaming, cleanup churn, template-driven restructure

**Immediate Operating Files**:
The scaled operating files that should exist now because the repo already needs live coordination and durable session memory.
_Avoid_: waiting for chaos, overbuilding every optional surface

**Deferred Operating Files**:
Scaled operating files that should wait until real pressure justifies them.
_Avoid_: day-one clutter, speculative structure

**Live Pointer**:
The small current-state surface that points to the active session, current question, next decision, and relevant review or proof artifacts.
_Avoid_: giant status doc, duplicate planning lane

**Durable Memory**:
Project memory that should persist across agents and sessions.
_Avoid_: session-local churn, transient state

**Session State**:
The moving truth for one dated work chain, captured in its session folder.
_Avoid_: permanent knowledge base, cross-project memory dump

**Inline Vocabulary Update**:
The rule that resolved terminology should be written into the living vocabulary files immediately rather than deferred to a later cleanup pass.
_Avoid_: batched glossary cleanup, terminology drift

**In-Place Refinement**:
The rule that future agents should strengthen existing workstream and product docs before creating parallel summary surfaces.
_Avoid_: duplicate truth, summary sprawl, avoidable bridge docs

**Uncertainty Surfacing**:
The rule that unresolved uncertainty should be named explicitly instead of being hidden behind confident-sounding operating instructions.
_Avoid_: fake certainty, polished ambiguity, premature closure

**Stability Label**:
A clear marker such as `hypothesis`, `working model`, `stable rule`, or `validated pattern` that signals how settled a statement currently is.
_Avoid_: mixed confidence, unlabeled assertions, hidden maturity

**Source Tracing**:
The rule that new operating claims should point back to the relevant source workstream, product, or research doc when the origin is not obvious.
_Avoid_: unsupported synthesis, magical conclusions, untraceable rules

**Research-to-Skill Conversion**:
The repo behavior of turning research, hypotheses, reviews, and vocabulary into stable skill-operating assets without prematurely collapsing into implementation.

**General Working Doctrine**:
The reusable repo-operating rules for writing, coding, collaboration, session hygiene, and execution behavior that can be inherited from a proven repo contract such as `cowork`.

**Presentation Incubation Doctrine**:
The presentation-specific repo rules that govern how research, hypotheses, reviews, and vocabulary become stable operating assets and eventually a production skill.
_Avoid_: coding-first behavior, premature productionization

**Authoritative Source Surfaces**:
The repo files and folders that future agents should read before writing or revising skill-operating instructions.
_Avoid_: generic skill writing from memory, skipping repo truth

**Skill Readiness Rule**:
The rule that a production `SKILL.md` should only be drafted or revised when the underlying operating decisions are stable enough for reuse.
_Avoid_: premature skill collapse, productionizing active research

**Skill Readiness Criteria**:
The minimum stable system elements required before a production `SKILL.md` is justified.
_Avoid_: vague readiness, volume-of-notes as readiness

## Relationships

- The **Presentation Capability System** contains one **Presentation Orchestrator**
- The **Presentation Orchestrator** should use a fixed set of **Work Phases** with optional skips and loops
- The default **Work Phases** are **Briefing**, **Deck Archetype Comparison**, **Narrative Shaping**, **Prototyping**, **Authoring**, and **Verification**
- The **Presentation Orchestrator** defaults to **Human-in-the-Loop Collaboration**
- In **Incubation Mode**, the **Presentation Orchestrator** should use **Decision Surfacing** for major choices
- **Audience** and **Visual Posture** are separate inputs
- **Organization Posture** is a separate input from **Audience** and **Communication Job**
- **Presenter Voice** is a separate input from **Audience**, **Organization Posture**, and **Communication Job**
- **Presenter Voice** should come from a reusable **Voice Profile** with light per-job tuning through a **Voice Variant**
- The **Presentation Orchestrator** should choose a **Deck Archetype** from a small closed catalog using **Communication Job**, **Audience**, **Organization Posture**, delivery mode, and stakes
- The current starter **Deck Archetype** catalog is sufficient for incubation and should be treated as the working baseline
- Within the current starter catalog, **Executive Decision Deck** is expected to be the most frequently used archetype and should be hardened first during incubation
- During incubation, **Executive Decision Deck** should be defined first as the reference archetype package, with nearby archetypes clarified against it
- The `core job` of **Executive Decision Deck** is to get a decision, approval, or directional commitment
- The `proof style` of **Executive Decision Deck** is decision-grade proof
- **Deck Archetype** should allow an **Organization Variant** when the same core structural mode needs different density or proof expression across organizational contexts
- For **Executive Decision Deck**, the density profile should be handled through **Organization Variants** rather than one universal default
- A `B2B` or enterprise-leaning **Organization Variant** of **Executive Decision Deck** should be more compressed and proof-dense
- A `B2C` or consumer-leaning **Organization Variant** of **Executive Decision Deck** should be lighter, cleaner, and less text-dense on the main path
- A **Deck Archetype** constrains density, proof style, pacing, appendix depth, and **Visual Posture**
- The **Style Pool** contains reusable **Style Systems**
- A **Deck Archetype** can pair with multiple **Style Systems**
- A **Style Variant** personalizes a selected **Style System** for a specific deck context
- **Deck Archetype Comparison** should happen before **Style System** selection
- The **Style Pool** should stay shared across the repo, with **Style Fit Tags** to guide selection
- In **Incubation Mode**, the **Presentation Orchestrator** should use **Deck Archetype Comparison** so the catalog can be tested and expanded
- The current open work on **Deck Archetype** is package shape, overlap boundaries, and criteria for when a new archetype should be added
- A first usable **Deck Archetype** package should include name, core job, best fit, avoid when, default audience and stakes pattern, density profile, proof style, pacing, appendix expectation, delivery posture, required slide-role emphasis, style implications, and nearby archetypes with boundary notes
- Later production behavior can tighten archetype selection once the catalog is more stable
- The **Taste Standard** should apply across internal and external **Audience** types
- **Presenter Voice** should shape title tone, note posture, and on-slide compression without overriding the **Communication Job**
- **Narrative Shaping** should establish the argument before **Presenter Voice** tuning is applied
- During incubation, major choices such as **Deck Archetype**, **Style System**, major narrative shifts, structural cuts, and rehydrated assumptions should be surfaced explicitly
- **System-Shaping Decisions** should leave a **Decision Artifact** when they would otherwise be lost
- Existing working docs are the default **Decision Artifact** surface; use an **ADR** only for hard-to-reverse, surprising tradeoffs
- This repo should use the **Scaled Operating Model** rather than a thin scaffold
- This repo should follow **Brownfield Preservation** and add an **Operating Layer** around the existing structure
- **Immediate Operating Files** should be `AGENTS.md`, `work/current.md`, `sessions/context.md`, and one dated session folder with `session.md`, `state.md`, `progress.md`, `plan.md`, and `verify.md`
- **Deferred Operating Files** should include `repo-direction.md`, `LEARNINGS.md`, `archive/sessions/`, and `docs/adr/` until real pressure appears
- `work/current.md` should act as the **Live Pointer** for the repo
- `sessions/context.md` should hold **Durable Memory**
- each dated session folder should hold **Session State** for that work chain only
- `AGENTS.md` in this repo should primarily govern **Research-to-Skill Conversion** behavior rather than coding behavior
- `AGENTS.md` in this repo should be split into **General Working Doctrine** and **Presentation Incubation Doctrine**
- The **General Working Doctrine** should inherit the intent of `cowork`'s coding doctrine but rewrite it for research, experimentation, and skill incubation in this repo
- The **General Working Doctrine** should inherit `cowork`'s writing doctrine more strongly than its coding doctrine because language quality is core to this repo's work
- The **Presentation Incubation Doctrine** should keep experimentation inside existing research, product, review, and workstream surfaces by default
- Draft skill files or helper markdowns should be created only when they add a genuinely needed operating surface rather than a parallel proto-skill
- A genuinely needed operating surface should exist only when it runs the workflow, prevents repeated confusion, holds structured information existing docs cannot hold cleanly, or creates a reusable review, proof, or execution artifact
- Repo language, flow names, and operating structures should stay simple enough for a strong spreadsheet-driven PM to understand quickly
- `AGENTS.md` should distinguish between documentation work and executable experiment work
- This repo remains an active research and experimentation space even after a production skill exists
- Future improvements may come from model capabilities, agentic capabilities, new tech stacks, or new OSS/packages, so the research loop should stay open after v1
- Executable experiments should remain non-canonical by default until they are explicitly promoted
- Promoted experiment learnings should land in living repo truth before they land in the production skill package
- Before promotion, executable experiments should live near the surface they are testing: `research/`, `workstreams/`, or `product/`, and only use a dedicated experiment folder when real runnable assets do not fit cleanly in docs
- A dedicated runnable-experiments folder should be added only when real clutter or repeated confusion appears
- A production `SKILL.md` should be treated as a downstream consumer of this repo's stabilized truth, not as the primary source where new rules are invented first
- `AGENTS.md` should require **Inline Vocabulary Update** when terms are resolved
- `AGENTS.md` should prefer **In-Place Refinement** of existing docs over parallel summaries unless a new surface clearly reduces confusion
- `AGENTS.md` should require **Uncertainty Surfacing** when the system is still being discovered
- `AGENTS.md` should require **Stability Labels** where hypotheses, working models, and stable rules would otherwise get mixed together
- `AGENTS.md` should require **Source Tracing** when a new operating claim's origin is not obvious
- `AGENTS.md` should point future agents to the **Authoritative Source Surfaces** before they write or revise skill instructions
- The **Authoritative Source Surfaces** are `README.md`, `CONTEXT.md`, `UBIQUITOUS_LANGUAGE.md`, relevant `workstreams/`, relevant `product/`, and relevant `research/`
- `AGENTS.md` should enforce the **Skill Readiness Rule** before a production `SKILL.md` is drafted or revised
- The **Skill Readiness Criteria** are stable domain language, the six **Work Phases**, **Deck Archetype** logic, **Style Pool** and **Style System** logic, **Presenter Voice** logic, **Slide Role** and **Slide Contract** logic, **Existing Deck Adaptation** and **Deck Rehydration** rules, and evaluation plus verification expectations
- The **Presentation Orchestrator** should collaborate with the human on the **Communication Job**, audience, narrative thesis, evidence, **Slide Plan**, and **Slide Contracts** before deck creation
- **Existing Deck Adaptation** is a first-class capability from v1
- When an incoming deck lacks sufficient upstream structure, **Deck Rehydration** must happen before **Existing Deck Adaptation**
- When needed, **Deck Rehydration** happens inside **Briefing** rather than as a separate top-level **Work Phase**
- A **Rehydration Package** must include the communication job, audience, organization posture, archetype choice or comparison, current slide inventory with inferred roles, evidence map or missing-evidence flags, explicit requested change, and editability or template constraints
- **Prototype JSON** is the planning source of truth until the **PPTX Build Gate** is passed
- A **Prototype Artifact** renders the **Prototype JSON** for review and iteration
- **Prototyping** is the default way to lock visual direction and approach before **Authoring**
- **Prototyping** should explore style inside the chosen **Deck Archetype**, not before the structural frame is clear
- **Prototyping** should use a **Prototype Tree** so direction can be selected efficiently before deeper refinement
- **Prototyping** should compare a few **Style Systems** or **Style Variants** rather than inventing every deck look from scratch
- **Slide Roles** should come from a small closed vocabulary shared across the system
- **Slide Contracts** should be global by slide role, with **Slide Contract Variants** when a **Deck Archetype** needs different behavior
- The **Slide Plan** and **Slide Contracts** are upstream inputs to the **Deck**
- A **Deck** serves exactly one primary **Communication Job**
- A **Use-Case Family** is a variation inside the **Presentation Capability System**, not a separate product
- The **Presentation Orchestrator** should adapt its **Work Phases** to the chosen **Use-Case Family**

## Example dialogue

> **Dev:** "If investor pitch and internal comms behave differently, are they separate skills?"
> **Domain expert:** "No. They are different **Use-Case Families** inside one **Presentation Capability System**, and the **Presentation Orchestrator** should adapt its **Work Phases** accordingly."
>
> **Dev:** "Should the orchestrator invent a fresh workflow every time?"
> **Domain expert:** "No. It should use a fixed set of **Work Phases** and only skip or loop phases when the job already has enough structure."
>
> **Dev:** "Can the orchestrator just generate a draft from a short prompt and skip the back-and-forth?"
> **Domain expert:** "No. This system defaults to **Human-in-the-Loop Collaboration**, so the operator stays involved in the high-judgment parts."
>
> **Dev:** "When do we actually create the PowerPoint?"
> **Domain expert:** "Only after the **Prototype JSON** has been reviewed through a **Prototype Artifact**, the **Slide Plan** is settled, and the human explicitly passes the **PPTX Build Gate**."
>
> **Dev:** "When you say 'consumer,' do you mean a consumer audience?"
> **Domain expert:** "No. Here that means a cleaner **Visual Posture** and a higher **Taste Standard**, which can apply to internal or external **Audience** types alike."
>
> **Dev:** "Why would a leadership pitch at SAP differ from one at Instagram if both are internal?"
> **Domain expert:** "Because **Organization Posture** changes what native credibility, density, polish, and restraint look like even when the **Audience** and **Communication Job** are similar."
>
> **Dev:** "Should we invent the presentation mode from scratch each time?"
> **Domain expert:** "No. The system should pick a **Deck Archetype** from a small closed catalog and adapt it to the specific **Organization Posture** and job."
>
> **Dev:** "Should deck style be generated from scratch every time too?"
> **Domain expert:** "No. We should choose from a **Style Pool**, select a **Style System**, and create a light **Style Variant** for the specific job when needed."
>
> **Dev:** "Should we split the style library into separate pools for different archetypes or organizations?"
> **Domain expert:** "No. Keep one shared **Style Pool**, but use **Style Fit Tags** so selection stays disciplined without fragmenting the library."
>
> **Dev:** "Should style exploration start before we choose the deck archetype?"
> **Domain expert:** "No. Run **Deck Archetype Comparison** first, then explore **Style Systems** inside that structural frame."
>
> **Dev:** "Can presenter voice just be folded into audience or style?"
> **Domain expert:** "No. **Presenter Voice** is its own input. It shapes how the deck sounds, but it should not override the **Communication Job**."
>
> **Dev:** "Should we invent presenter voice from scratch every time?"
> **Domain expert:** "No. Start from a reusable **Voice Profile**, tune it lightly with a **Voice Variant**, and apply that after the narrative is structurally sound."
>
> **Dev:** "Should each deck archetype have a completely separate slide-contract system?"
> **Domain expert:** "No. Start with shared **Slide Contracts** by role, then add **Slide Contract Variants** only where the archetype meaningfully changes the role."
>
> **Dev:** "Should each deck archetype invent its own slide-role names too?"
> **Domain expert:** "No. Keep **Slide Roles** in a small closed shared vocabulary, then let archetypes change behavior through **Slide Contract Variants**."
>
> **Dev:** "If the system is pretty sure, can it just make big decisions silently to save time?"
> **Domain expert:** "Not in incubation. Use **Decision Surfacing** so major choices stay visible and reviewable while we are still learning the system."
>
> **Dev:** "Do all surfaced decisions need their own file?"
> **Domain expert:** "No. Only **System-Shaping Decisions** need a durable **Decision Artifact**. Small deck-level choices can stay in the living flow."
>
> **Dev:** "Should we write ADRs for most of these system decisions?"
> **Domain expert:** "No. Prefer the existing working docs, and use an **ADR** only when the tradeoff is hard to reverse and would otherwise be surprising later."
>
> **Dev:** "Does this repo still qualify for a thin setup?"
> **Domain expert:** "No. It already needs the **Scaled Operating Model** because the work is research-heavy, multi-stream, and full of durable system decisions."
>
> **Dev:** "Should we reorganize the repo now that we know it needs a scaled setup?"
> **Domain expert:** "No. Follow **Brownfield Preservation**: keep the current research structure and add the **Operating Layer** around it."
>
> **Dev:** "Which scaled operating files should we create immediately?"
> **Domain expert:** "Create the **Immediate Operating Files** now, and leave the **Deferred Operating Files** for when the repo actually needs them."
>
> **Dev:** "What is `work/current.md` for?"
> **Domain expert:** "It is the **Live Pointer**: a tiny surface that tells us what is active right now, what the next decision is, and which session or review matters."
>
> **Dev:** "What belongs in `sessions/context.md` versus the dated session folder?"
> **Domain expert:** "`sessions/context.md` holds **Durable Memory** across sessions, while the dated session folder holds the **Session State** for one moving work chain."
>
> **Dev:** "Should we wait and clean up the vocabulary later once more of the system is known?"
> **Domain expert:** "No. Use **Inline Vocabulary Update** so repo truth stays aligned with the decisions as they are made."
>
> **Dev:** "Should future agents make lots of summary docs as they synthesize the repo?"
> **Domain expert:** "No. Use **In-Place Refinement** first, and add a new summary surface only when it clearly reduces confusion."
>
> **Dev:** "Should future agents smooth over unresolved gaps so the skill sounds more complete?"
> **Domain expert:** "No. Use **Uncertainty Surfacing** so active unknowns stay visible until they are actually resolved."
>
> **Dev:** "How do we keep hypotheses from blending into stable rules?"
> **Domain expert:** "Use a **Stability Label** so each important claim shows whether it is a hypothesis, working model, stable rule, or validated pattern."
>
> **Dev:** "If a future agent writes a new operating rule, how do we know where it came from?"
> **Domain expert:** "Use **Source Tracing** so the claim can be tied back to the relevant workstream, product, or research source when the origin is not already obvious."
>
> **Dev:** "Should `AGENTS.md` mostly govern coding practice here?"
> **Domain expert:** "No. In this repo it should mostly govern **Research-to-Skill Conversion** behavior, because the primary work is turning research into a stable skill system."
>
> **Dev:** "Should this repo's `AGENTS.md` blend all rules together in one block?"
> **Domain expert:** "No. Split it into **General Working Doctrine** and **Presentation Incubation Doctrine** so the inherited operating rules stay distinct from the presentation-specific incubation rules."
>
> **Dev:** "Should the coding doctrine come over from `cowork` unchanged?"
> **Domain expert:** "No. Keep the anti-slop intent because it guards against common LLM pitfalls, but rewrite it for research, experimentation, and skill incubation rather than production app delivery."
>
> **Dev:** "Should the writing doctrine also be softened the same way?"
> **Domain expert:** "No. Inherit the writing doctrine more strongly. This repo's main work is language, reasoning, and operating clarity, so writing discipline is core behavior here."
>
> **Dev:** "Should future agents be free to make draft skill files and helper docs as they experiment?"
> **Domain expert:** "No. Keep experimentation in the existing repo surfaces by default. Create draft skill files or helper markdowns only when they solve a real operating need instead of creating a parallel proto-skill."
>
> **Dev:** "What counts as a real operating need for a new surface?"
> **Domain expert:** "Create a new surface only when it runs the workflow, prevents repeated confusion, holds structured information existing docs cannot hold cleanly, or creates a reusable review, proof, or execution artifact."
>
> **Dev:** "Should repo language be allowed to get abstract if the system is sophisticated?"
> **Domain expert:** "No. Keep the language, flow names, and operating structures simple enough that a strong spreadsheet-driven PM can understand them quickly."
>
> **Dev:** "Should `AGENTS.md` distinguish between documentation work and executable experiment work?"
> **Domain expert:** "Yes. The repo spans both, and each needs different expectations even though both should stay grounded in the same source truth."
>
> **Dev:** "Does experimentation end once we ship v1 of the skill?"
> **Domain expert:** "No. This repo should stay the active research and experimentation space even after a production skill exists, because improvements may come from new models, agentic capabilities, tech stacks, or OSS."
>
> **Dev:** "Should experiments become canonical automatically once we have a production skill?"
> **Domain expert:** "No. Keep experiments non-canonical by default even after v1. Promotion into stable doctrine, reusable assets, or production skill behavior should stay explicit."
>
> **Dev:** "When an experiment is worth promoting, should it go straight into the skill package?"
> **Domain expert:** "No. Promote it into living repo truth first, then let the production skill inherit from that stabilized source."
>
> **Dev:** "Where should experiments live before promotion?"
> **Domain expert:** "Keep them close to the surface they are testing: `research/` for hypothesis work, `workstreams/` for operating-method experiments, `product/` for reusable system shaping, and use a dedicated experiment folder only when real runnable assets do not fit cleanly in docs."
>
> **Dev:** "Should we add a top-level experiments folder now so we are ready?"
> **Domain expert:** "No. Wait for real pressure. Add it only when runnable assets start causing clutter or repeated confusion."
>
> **Dev:** "Should the production skill be allowed to become the first place where new rules are written?"
> **Domain expert:** "No. Treat the production `SKILL.md` as a downstream consumer of stabilized repo truth, not the primary source where new rules are invented first."
>
> **Dev:** "What should future agents read before they write skill instructions here?"
> **Domain expert:** "Start with the **Authoritative Source Surfaces** so instruction-writing stays grounded in repo truth rather than generic habit."
>
> **Dev:** "Can a future agent draft the production skill as soon as there is a lot of research text?"
> **Domain expert:** "No. Follow the **Skill Readiness Rule**: a production `SKILL.md` waits until the key operating decisions are stable enough for reuse."
>
> **Dev:** "What counts as stable enough?"
> **Domain expert:** "Meet the **Skill Readiness Criteria**. If those core system elements are still being reinvented, the repo can make drafts and prototypes but not a production skill."
>
> **Dev:** "Why show multiple archetypes instead of just recommending one?"
> **Domain expert:** "Because this repo is still incubating the catalog, so **Deck Archetype Comparison** helps us learn where the current archetypes fit poorly or where a new one is missing."
>
> **Dev:** "Will the production skill always show multiple options too?"
> **Domain expert:** "Not necessarily. In **Incubation Mode** we compare archetypes by default to learn the taxonomy, then we can tighten the default later once the catalog is stable."
>
> **Dev:** "If someone hands us an old deck with no brief or structure notes, can we just edit the slides directly?"
> **Domain expert:** "No. If the upstream context is missing, we run **Deck Rehydration** first, then do **Existing Deck Adaptation** against that restored structure."
>
> **Dev:** "How much context do we need before adapting the deck?"
> **Domain expert:** "At minimum we need the **Rehydration Package**. If we cannot recover that confidently, the system should pause instead of pretending the update is safe."
>
> **Dev:** "Should we just show one polished prototype direction?"
> **Domain expert:** "No. **Prototyping** should use a **Prototype Tree**: compare a few strong directions first, then go deeper only on the chosen one."

## Flagged ambiguities

- "skill" was used to mean both the top-level interface and internal helpers; resolved as **Presentation Orchestrator** for the top-level entry point and **Work Phase** for the major internal phases
- "workflow" could mean the stable operating sequence or one-off execution path; resolved here as a fixed set of **Work Phases**
- "slides, decks, powerpoints, presentations" were used interchangeably; resolved as **Deck** for the editable artifact and **Presentation Capability System** for the broader domain
- "all sorts of use cases" could imply multiple products; resolved as **Use-Case Families** within one system
- "human-in-the-loop" could mean minor approvals or deep collaboration; resolved here as the default operating mode for the whole **Presentation Orchestrator**
- "visual json prototypes" and similar phrasing are resolved as **Prototype JSON** for the structured source and **Prototype Artifact** for the rendered review surface
- "strict pptx to be created" is resolved as the **PPTX Build Gate**, an explicit approval step rather than the default outcome of early exploration
- "consumer" was used in a way that could imply market or audience; resolved here as a **Visual Posture** and **Taste Standard** reference instead
- "organizational difference" could be mistaken for audience difference; resolved here as **Organization Posture**
- "presenter voice" could be mistaken for audience, posture, or style; resolved here as **Presenter Voice**
- "voice library versus fresh voice" is resolved here as **Voice Profile** plus **Voice Variant**
- "global versus archetype-specific slide contracts" is resolved here as base **Slide Contracts** plus **Slide Contract Variants**
- "global versus archetype-specific slide roles" is resolved here as a closed shared set of **Slide Roles**
- "deck style" could ambiguously mean structural mode or visual execution; resolved here as **Deck Archetype** for structure and **Style System** for reusable visual execution
- "archetype comparison" was too ambiguous on its own; resolved here as **Deck Archetype Comparison**
- "show options" could be mistaken for indecision; resolved here as **Deck Archetype Comparison** during incubation
- "during incubation, then tighten later" is resolved here as **Incubation Mode** with different default behavior from the later production skill
- "update" could mean direct slide edits or structured revision; resolved here as **Existing Deck Adaptation**
- "new deck provided without the orchestratory process" is resolved here as a trigger for **Deck Rehydration**
- "minimum recovered context" is resolved here as the **Rehydration Package**
- "tree style approach" is resolved here as **Prototype Tree**
- "style pool and personalized style" are resolved here as **Style Pool**, **Style System**, and **Style Variant**
- "shared pool with families or tags" is resolved here as a shared **Style Pool** with **Style Fit Tags**
- "archetype versus style ordering" is resolved here as **Deck Archetype Comparison** before **Style System** selection
- "silent collapsing versus explicit review" is resolved here as **Decision Surfacing** during incubation
- "durable artifact versus living docs only" is resolved here as **Decision Artifact** for **System-Shaping Decisions**
- "ADR versus living docs" is resolved here as living docs by default and **ADR** only for hard-to-reverse surprising tradeoffs
- "thin versus scaled repo setup" is resolved here as **Scaled Operating Model**
- "preserve structure versus reorganize now" is resolved here as **Brownfield Preservation** plus an **Operating Layer**
- "immediate versus later operating files" is resolved here as **Immediate Operating Files** and **Deferred Operating Files**
- "`work/current.md` purpose" is resolved here as the **Live Pointer**
- "persistent memory versus per-session state" is resolved here as **Durable Memory** and **Session State**
- "update vocabulary now versus later" is resolved here as **Inline Vocabulary Update**
- "refine existing docs versus create parallel summaries" is resolved here as **In-Place Refinement**
- "hide uncertainty versus surface it" is resolved here as **Uncertainty Surfacing**
- "hypothesis versus stable rule labeling" is resolved here as **Stability Label**
- "where a synthesized rule came from" is resolved here as **Source Tracing**
- "`AGENTS.md` focus" is resolved here as **Research-to-Skill Conversion** behavior first
- "`AGENTS.md` structure" is resolved here as **General Working Doctrine** plus **Presentation Incubation Doctrine**
- "`cowork` coding doctrine reuse" is resolved here as inherit intent, rewrite for incubation
- "`cowork` writing doctrine reuse" is resolved here as inherit strongly with light adaptation
- "where experimentation should live" is resolved here as in-place incubation first, new helper surfaces only when clearly needed
- "what justifies a new operating surface" is resolved here as real workflow need, not summary duplication
- "how simple repo language should stay" is resolved here as PM-legible language by default
- "doc work versus executable experiment work" is resolved here as an explicit distinction in `AGENTS.md`
- "whether research stops after v1" is resolved here as no, the repo stays an active evolution space
- "how experimental outputs become canon" is resolved here as explicit promotion only
- "where promoted experiment learnings land first" is resolved here as living repo truth before skill package
- "where experiments live before promotion" is resolved here as near the tested surface, with a dedicated experiment folder only when needed
- "when to add a dedicated experiments folder" is resolved here as only after real pressure appears
- "what the production skill is relative to this repo" is resolved here as downstream consumer, not primary source
- "what must be read before instruction writing" is resolved here as the **Authoritative Source Surfaces**
- "when a production skill can be written" is resolved here as the **Skill Readiness Rule**
- "what counts as stable enough" is resolved here as the **Skill Readiness Criteria**
