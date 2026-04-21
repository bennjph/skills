# Ubiquitous Language

## System and workflow

| Term | Definition | Aliases to avoid |
| --- | --- | --- |
| **Presentation Capability System** | The single domain incubated in this repo for creating, adapting, and verifying professional presentation decks. | Multiple products, deck factory, shared skills repo |
| **Presentation Orchestrator** | The top-level skill entry point that runs the presentation workflow end to end. | Monolithic prompt, manual skill bundle |
| **Work Phase** | A named phase of work the orchestrator moves through while shaping, building, adapting, or verifying a deck. | Stage, deck stage, ad hoc step |
| **Incubation Mode** | The current R&D phase where the system stays exploratory so categories, workflows, and gaps can be discovered before the production skill is tightened. | Final production behavior, frozen operating model |
| **Human-in-the-Loop Collaboration** | The default operating mode where the system works with a human through key judgment steps instead of treating the deck as a one-shot generation task. | Fire-and-forget automation, one-shot generation |
| **Decision Surfacing** | The rule that major system choices are shown explicitly to the human instead of being silently collapsed by the orchestrator. | Hidden automation, silent major decisions |
| **System-Shaping Decision** | A choice that changes the presentation system itself rather than only affecting one deck run. | Tiny judgment call, one-off deck tweak |
| **Decision Artifact** | A durable repo artifact that records a system-shaping decision when future work would otherwise lose the reasoning. | Transient chat only, file for every tiny choice |
| **ADR** | A narrowly used decision record for a hard-to-reverse, surprising tradeoff that future readers would otherwise re-litigate. | Default note format, record for every system choice |
| **Scaled Operating Model** | The richer repo operating shape used when durable memory, layered docs, and multi-workstream coordination are core to the work. | Thin scaffold, minimal handoff only |
| **Operating Layer** | The repo-operating files added around the existing brownfield content to provide live pointers, durable memory, and coordination surfaces. | Full repo reorganization, duplicate document lanes |
| **Brownfield Preservation** | The rule that the current research and product structure should stay in place while the operating layer is added around it. | Needless renaming, cleanup churn, template-driven restructure |
| **Immediate Operating Files** | The scaled operating files that should exist now because the repo already needs live coordination and durable session memory. | Waiting for chaos, overbuilding every optional surface |
| **Deferred Operating Files** | Scaled operating files that should wait until real pressure justifies them. | Day-one clutter, speculative structure |
| **Live Pointer** | The small current-state surface that points to the active session, current question, next decision, and relevant review or proof artifacts. | Giant status doc, duplicate planning lane |
| **Durable Memory** | Project memory that should persist across agents and sessions. | Session-local churn, transient state |
| **Session State** | The moving truth for one dated work chain, captured in its session folder. | Permanent knowledge base, cross-project memory dump |
| **Inline Vocabulary Update** | The rule that resolved terminology should be written into the living vocabulary files immediately rather than deferred to a later cleanup pass. | Batched glossary cleanup, terminology drift |
| **In-Place Refinement** | The rule that future agents should strengthen existing workstream and product docs before creating parallel summary surfaces. | Duplicate truth, summary sprawl, avoidable bridge docs |
| **Uncertainty Surfacing** | The rule that unresolved uncertainty should be named explicitly instead of being hidden behind confident-sounding operating instructions. | Fake certainty, polished ambiguity, premature closure |
| **Stability Label** | A clear marker such as `hypothesis`, `working model`, `stable rule`, or `validated pattern` that signals how settled a statement currently is. | Mixed confidence, unlabeled assertions, hidden maturity |
| **Source Tracing** | The rule that new operating claims should point back to the relevant source workstream, product, or research doc when the origin is not obvious. | Unsupported synthesis, magical conclusions, untraceable rules |
| **Research-to-Skill Conversion** | The repo behavior of turning research, hypotheses, reviews, and vocabulary into stable skill-operating assets without prematurely collapsing into implementation. | Coding-first behavior, premature productionization |
| **General Working Doctrine** | The reusable repo-operating rules for writing, coding, collaboration, session hygiene, and execution behavior that can be inherited from a proven repo contract such as `cowork`. | Presentation-specific incubation rules, machine-local defaults |
| **Presentation Incubation Doctrine** | The presentation-specific repo rules that govern how research, hypotheses, reviews, and vocabulary become stable operating assets and eventually a production skill. | Generic repo doctrine, final reusable skill behavior |
| **Authoritative Source Surfaces** | The repo files and folders that future agents should read before writing or revising skill-operating instructions. | Generic skill writing from memory, skipping repo truth |
| **Skill Readiness Rule** | The rule that a production `SKILL.md` should only be drafted or revised when the underlying operating decisions are stable enough for reuse. | Premature skill collapse, productionizing active research |
| **Skill Readiness Criteria** | The minimum stable system elements required before a production `SKILL.md` is justified. | Vague readiness, volume-of-notes as readiness |

## Job framing and fit

| Term | Definition | Aliases to avoid |
| --- | --- | --- |
| **Communication Job** | The change in understanding, belief, or decision the deck is meant to create in its audience. | Slide request, content dump |
| **Presenter Voice** | The characteristic way the presenter should sound across titles, on-slide copy, and speaker notes. | Audience, organization posture, visual style |
| **Voice Profile** | A reusable tone and expression profile that defines how a presenter typically sounds across presentation work. | One-off tone invention, visual style |
| **Voice Variant** | A light job-specific tuning of a selected voice profile for a particular presentation context. | Full rewrite of presenter identity, ad hoc tone drift |
| **Use-Case Family** | A recurring presentation situation with distinct audience, stakes, and evidence patterns inside the same system. | Separate product, vertical |
| **Audience** | The specific people the deck is trying to move, such as colleagues, vendors, customers, executives, or investors. | Visual style, market category |
| **Organization Posture** | The cultural and stylistic expectations of the organization or brand context the deck must feel native to. | Audience, communication job, template only |
| **Deck Archetype** | A reusable presentation mode that pre-decides density, proof style, pacing, appendix depth, and visual posture for a class of jobs. | One-off style invention, generic template only |
| **Deck Archetype Comparison** | Presenting multiple plausible deck archetypes side by side so the operator can scrutinize fit and expose missing archetypes. | Indecision, hidden classification, unqualified archetype comparison |
| **Organization Variant** | An organization-specific adaptation of a deck archetype that changes density, proof expression, or visible restraint without changing the core structural job. Use `Org Variant` as the short form. | Separate archetype, style system only, brand template |
| **Style Pool** | A curated reusable library of visual systems available for selection and adaptation across deck jobs. | One-off style generation, random template pile |
| **Style System** | A reusable visual execution system covering typography, grids, theme, spacing, chart treatment, and motion posture. | Deck archetype, template screenshot, mood board only |
| **Style Variant** | A job-specific personalization of a selected style system for a particular organization posture, communication job, or deck. | Brand-new style invention, manual per-slide override set |
| **Style Fit Tags** | Metadata on a style system that indicates which organization postures, deck archetypes, or presentation situations it fits best. | Hard partitioning, implied universal fit |
| **Visual Posture** | The chosen visual character of the deck, including simplicity, polish, density, and restraint, independent of audience type. | Audience type, market segment |
| **Taste Standard** | The cross-cutting expectation that decks should feel deliberate, clean, modern, and high-signal rather than stale, cluttered, or generic. | Optional polish, decoration layer |

## Planning and authoring artifacts

| Term | Definition | Aliases to avoid |
| --- | --- | --- |
| **Prototype JSON** | The structured planning source of truth that captures the communication job, audience, narrative, evidence, and slide plan before deck creation. | Final deliverable, raw prose blob |
| **Prototype Artifact** | An inspectable visual rendering of the Prototype JSON used to review options, sequence, density, and story before deck creation. | Final deck, polished deliverable |
| **Prototype Tree** | A progressive branching approach to prototyping where early rounds compare a few distinct directions and later rounds go deeper on the selected direction. | Flat style dump, full polish on every option, one-shot visual choice |
| **Slide Role** | A named job a slide performs in the deck, such as context, proof, comparison, recommendation, or appendix evidence. | Arbitrary slide label, per-archetype invention |
| **Slide Plan** | The ordered definition of slide roles, titles, evidence, and visual intent that the deck build consumes. | Rough outline, ad hoc slide list |
| **Slide Contract** | A structured definition of what a slide type must do, show, and preserve before rendering or update work begins. | Loose prompt fragment, layout guess |
| **Slide Contract Variant** | An archetype-specific adaptation of a base slide contract for when the same slide role needs different proof, density, or layout behavior. | Entirely separate contract universe, per-deck reinvention |
| **PPTX Build Gate** | The explicit approval point after prototype review where the system is allowed to create or update the final editable PowerPoint deck. | Default behavior, automatic generation |
| **Deck** | The editable presentation artifact produced or updated for a specific communication job. | PowerPoint as the domain name, generic file |

## Adaptation and maintenance

| Term | Definition | Aliases to avoid |
| --- | --- | --- |
| **Existing Deck Adaptation** | Updating a provided deck while preserving or deliberately reshaping its narrative, structure, and editability rather than patching slide surfaces blindly. | Direct slide surgery, cosmetic-only revision |
| **Deck Rehydration** | Reconstructing missing upstream context such as communication job, audience, archetype, slide roles, and evidence map before adapting an existing deck. | Blind patching, context-free editing |
| **Rehydration Package** | The minimum recovered context required before an existing deck can be safely adapted. | Partial guesswork, implied understanding |

## Relationships

- The **Presentation Capability System** contains one **Presentation Orchestrator**
- The **Presentation Orchestrator** uses a fixed set of **Work Phases**
- The default **Work Phases** are **Briefing**, **Deck Archetype Comparison**, **Narrative Shaping**, **Prototyping**, **Authoring**, and **Verification**
- **Human-in-the-Loop Collaboration** is the default operating mode of the **Presentation Orchestrator**
- In **Incubation Mode**, the **Presentation Orchestrator** should use **Decision Surfacing** for major choices
- A **Communication Job** is carried by exactly one primary **Deck**
- A **Use-Case Family** is a variation inside the **Presentation Capability System**, not a separate product
- **Presenter Voice** is a separate input from **Audience**, **Organization Posture**, and **Communication Job**
- **Presenter Voice** should come from a reusable **Voice Profile** with light per-job tuning through a **Voice Variant**
- **Audience**, **Organization Posture**, and **Communication Job** jointly influence **Deck Archetype**
- The current starter **Deck Archetype** catalog is sufficient for incubation and should be treated as the working baseline
- Within the current starter catalog, **Executive Decision Deck** is expected to be the most frequently used archetype and should be hardened first during incubation
- During incubation, **Executive Decision Deck** should be defined first as the reference archetype package, with nearby archetypes clarified against it
- The `core job` of **Executive Decision Deck** is to get a decision, approval, or directional commitment
- The `proof style` of **Executive Decision Deck** is decision-grade proof
- **Deck Archetype** should allow an **Organization Variant** when the same core structural mode needs different density or proof expression across organizational contexts
- For **Executive Decision Deck**, the density profile should be handled through **Organization Variants** rather than one universal default
- A `B2B` or enterprise-leaning **Organization Variant** of **Executive Decision Deck** should be more compressed and proof-dense
- A `B2C` or consumer-leaning **Organization Variant** of **Executive Decision Deck** should be lighter, cleaner, and less text-dense on the main path
- A **Deck Archetype** constrains **Visual Posture**, density, proof style, pacing, and appendix depth
- The **Style Pool** contains reusable **Style Systems**
- A **Deck Archetype** can pair with multiple **Style Systems**
- A **Style Variant** personalizes a selected **Style System** for a specific deck context
- **Deck Archetype Comparison** should happen before **Style System** selection
- The **Style Pool** should stay shared across the repo, with **Style Fit Tags** to guide selection
- In **Incubation Mode**, the orchestrator uses **Deck Archetype Comparison** to test and expand the archetype catalog
- The current open work on **Deck Archetype** is package shape, overlap boundaries, and criteria for when a new archetype should be added
- A first usable **Deck Archetype** package should include name, core job, best fit, avoid when, default audience and stakes pattern, density profile, proof style, pacing, appendix expectation, delivery posture, required slide-role emphasis, style implications, and nearby archetypes with boundary notes
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
- **Prototype JSON** is the planning source of truth until the **PPTX Build Gate** is passed
- A **Prototype Artifact** renders the **Prototype JSON** for review and iteration
- **Prototyping** is the default way to lock visual direction and approach before **Authoring**
- **Prototyping** should explore style inside the chosen **Deck Archetype**, not before the structural frame is clear
- **Prototyping** should use a **Prototype Tree** so direction can be selected efficiently before deeper refinement
- **Prototyping** should compare a few **Style Systems** or **Style Variants** rather than inventing every deck look from scratch
- **Slide Roles** should come from a small closed vocabulary shared across the system
- **Slide Contracts** should be global by slide role, with **Slide Contract Variants** when a **Deck Archetype** needs different behavior
- The **Slide Plan** and **Slide Contract** are upstream inputs to the **Deck**
- **Existing Deck Adaptation** is allowed only after **Deck Rehydration** produces the **Rehydration Package**
- When needed, **Deck Rehydration** happens inside **Briefing** rather than as a separate top-level **Work Phase**

## Example dialogue

> **Dev:** "If I upload an old SAP leadership deck and ask for a cleaner Instagram-level feel, is that a new product or just a style tweak?"
> **Domain expert:** "Neither. It is **Existing Deck Adaptation**, and we first need **Deck Rehydration** so we understand the **Communication Job**, **Audience**, and **Organization Posture**."
> **Dev:** "So the same leadership audience could still lead to different results?"
> **Domain expert:** "Yes. **Audience** and **Organization Posture** are separate inputs, and they can point to different **Deck Archetypes** and **Visual Postures**."
> **Dev:** "Do we go straight to PowerPoint once we infer that?"
> **Domain expert:** "No. We work through the **Work Phases**, review the **Prototype Artifact**, and only cross the **PPTX Build Gate** when the upstream structure is solid."
> **Dev:** "Should we fully polish every visual option before choosing?"
> **Domain expert:** "No. Use a **Prototype Tree**: compare a few strong directions first, then deepen the chosen one."
> **Dev:** "Do we invent the visual system fresh every time?"
> **Domain expert:** "No. Choose from the **Style Pool**, pick a **Style System**, and make a light **Style Variant** only if the job needs personalization."
> **Dev:** "Should we split the style library into separate pools for each context?"
> **Domain expert:** "No. Keep one shared **Style Pool** and use **Style Fit Tags** so the right systems surface for each job."
> **Dev:** "Should style exploration happen before we know the deck archetype?"
> **Domain expert:** "No. Choose the **Deck Archetype** first, then compare **Style Systems** within that frame."
> **Dev:** "Can presenter voice just be treated as audience or style?"
> **Domain expert:** "No. **Presenter Voice** is its own input. It shapes how the deck sounds, but it should not override the **Communication Job**."
> **Dev:** "Should we invent presenter voice from scratch every time?"
> **Domain expert:** "No. Start from a reusable **Voice Profile**, tune it lightly with a **Voice Variant**, and apply that after the narrative is structurally sound."
> **Dev:** "Should each deck archetype have a completely separate slide-contract system?"
> **Domain expert:** "No. Start with shared **Slide Contracts** by role, then add **Slide Contract Variants** only where the archetype meaningfully changes the role."
> **Dev:** "Should each deck archetype invent its own slide-role names too?"
> **Domain expert:** "No. Keep **Slide Roles** in a small closed shared vocabulary, then let archetypes change behavior through **Slide Contract Variants**."
> **Dev:** "If the system is pretty sure, can it just make big decisions silently to save time?"
> **Domain expert:** "Not in incubation. Use **Decision Surfacing** so major choices stay visible and reviewable while we are still learning the system."
> **Dev:** "Do all surfaced decisions need their own file?"
> **Domain expert:** "No. Only **System-Shaping Decisions** need a durable **Decision Artifact**. Small deck-level choices can stay in the living flow."
> **Dev:** "Should we write ADRs for most of these system decisions?"
> **Domain expert:** "No. Prefer the existing working docs, and use an **ADR** only when the tradeoff is hard to reverse and would otherwise be surprising later."
> **Dev:** "Does this repo still qualify for a thin setup?"
> **Domain expert:** "No. It already needs the **Scaled Operating Model** because the work is research-heavy, multi-stream, and full of durable system decisions."
> **Dev:** "Should we reorganize the repo now that we know it needs a scaled setup?"
> **Domain expert:** "No. Follow **Brownfield Preservation**: keep the current research structure and add the **Operating Layer** around it."
> **Dev:** "Which scaled operating files should we create immediately?"
> **Domain expert:** "Create the **Immediate Operating Files** now, and leave the **Deferred Operating Files** for when the repo actually needs them."
> **Dev:** "What is `work/current.md` for?"
> **Domain expert:** "It is the **Live Pointer**: a tiny surface that tells us what is active right now, what the next decision is, and which session or review matters."
> **Dev:** "What belongs in `sessions/context.md` versus the dated session folder?"
> **Domain expert:** "`sessions/context.md` holds **Durable Memory** across sessions, while the dated session folder holds the **Session State** for one moving work chain."
> **Dev:** "Should we wait and clean up the vocabulary later once more of the system is known?"
> **Domain expert:** "No. Use **Inline Vocabulary Update** so repo truth stays aligned with the decisions as they are made."
> **Dev:** "Should future agents make lots of summary docs as they synthesize the repo?"
> **Domain expert:** "No. Use **In-Place Refinement** first, and add a new summary surface only when it clearly reduces confusion."
> **Dev:** "Should future agents smooth over unresolved gaps so the skill sounds more complete?"
> **Domain expert:** "No. Use **Uncertainty Surfacing** so active unknowns stay visible until they are actually resolved."
> **Dev:** "How do we keep hypotheses from blending into stable rules?"
> **Domain expert:** "Use a **Stability Label** so each important claim shows whether it is a hypothesis, working model, stable rule, or validated pattern."
> **Dev:** "If a future agent writes a new operating rule, how do we know where it came from?"
> **Domain expert:** "Use **Source Tracing** so the claim can be tied back to the relevant workstream, product, or research source when the origin is not already obvious."
> **Dev:** "Should `AGENTS.md` mostly govern coding practice here?"
> **Domain expert:** "No. In this repo it should mostly govern **Research-to-Skill Conversion** behavior, because the primary work is turning research into a stable skill system."
> **Dev:** "What should future agents read before they write skill instructions here?"
> **Domain expert:** "Start with the **Authoritative Source Surfaces** so instruction-writing stays grounded in repo truth rather than generic habit."
> **Dev:** "Can a future agent draft the production skill as soon as there is a lot of research text?"
> **Domain expert:** "No. Follow the **Skill Readiness Rule**: a production `SKILL.md` waits until the key operating decisions are stable enough for reuse."
> **Dev:** "What counts as stable enough?"
> **Domain expert:** "Meet the **Skill Readiness Criteria**. If those core system elements are still being reinvented, the repo can make drafts and prototypes but not a production skill."

## Flagged ambiguities

- "skill" was used to mean both the top-level system interface and its internal helpers; use **Presentation Orchestrator** for the top-level entry point and **Work Phase** for the major internal phases.
- "slides," "decks," "PowerPoints," and "presentations" were used interchangeably; use **Deck** for the editable artifact and **Presentation Capability System** for the broader domain.
- "consumer" was initially ambiguous between market type and design sensibility; use **Visual Posture** and **Taste Standard** when referring to the cleaner, simpler, higher-taste look.
- Organization-specific differences like SAP versus Instagram could be mistaken for audience differences; use **Organization Posture** for that distinction.
- "Presenter voice" can be mistaken for audience, posture, or style; use **Presenter Voice** as a separate input.
- "Voice library versus fresh voice" was unclear; use **Voice Profile** plus **Voice Variant**.
- "Deck style" can mean structure or visuals; use **Deck Archetype** for structural mode and **Style System** for reusable visual execution.
- "Archetype comparison" is ambiguous on its own; use **Deck Archetype Comparison** when multiple plausible deck archetypes are intentionally surfaced during **Incubation Mode**.
- "Show options" could sound like indecision; use **Deck Archetype Comparison** when multiple plausible deck archetypes are intentionally surfaced during **Incubation Mode**.
- "Update" could mean direct slide patching or structured revision; use **Existing Deck Adaptation** for the structured path and **Deck Rehydration** when upstream context is missing.
- "workflow" could mean the stable operating sequence or a one-off execution path; use the fixed set of **Work Phases** for the stable named sequence.
- "tree style approach" was informal; use **Prototype Tree** for the progressive branching prototyping method.
- "Style pool and personalized style" were informal; use **Style Pool**, **Style System**, and **Style Variant**.
- "Shared pool with families or tags" was informal; use a shared **Style Pool** with **Style Fit Tags**.
- "Archetype versus style ordering" was unclear; use **Deck Archetype Comparison** before **Style System** selection.
- "Global versus archetype-specific slide contracts" was unclear; use base **Slide Contracts** plus **Slide Contract Variants**.
- "Global versus archetype-specific slide roles" was unclear; use a closed shared set of **Slide Roles**.
- "Silent collapsing versus explicit review" was unclear; use **Decision Surfacing** during **Incubation Mode**.
- "Durable artifact versus living docs only" was unclear; use **Decision Artifact** for **System-Shaping Decisions**.
- "ADR versus living docs" was unclear; use living docs by default and **ADR** only for hard-to-reverse surprising tradeoffs.
- "Thin versus scaled repo setup" was unclear; use the **Scaled Operating Model**.
- "Preserve structure versus reorganize now" was unclear; use **Brownfield Preservation** plus an **Operating Layer**.
- "Immediate versus later operating files" was unclear; use **Immediate Operating Files** and **Deferred Operating Files**.
- "`work/current.md` purpose" was unclear; use the **Live Pointer**.
- "Persistent memory versus per-session state" was unclear; use **Durable Memory** and **Session State**.
- "Update vocabulary now versus later" was unclear; use **Inline Vocabulary Update**.
- "Refine existing docs versus create parallel summaries" was unclear; use **In-Place Refinement**.
- "Hide uncertainty versus surface it" was unclear; use **Uncertainty Surfacing**.
- "Hypothesis versus stable rule labeling" was unclear; use **Stability Label**.
- "Where a synthesized rule came from" was unclear; use **Source Tracing**.
- "`AGENTS.md` focus" was unclear; use **Research-to-Skill Conversion** behavior first.
- "What must be read before instruction writing" was unclear; use the **Authoritative Source Surfaces**.
- "When a production skill can be written" was unclear; use the **Skill Readiness Rule**.
- "What counts as stable enough" was unclear; use the **Skill Readiness Criteria**.
