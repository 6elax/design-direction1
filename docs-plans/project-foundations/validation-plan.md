# Co-Align Validation Plan

<!-- Validation strategy for research-led social innovation projects. Core hypotheses and research questions define what we're trying to learn; the MVP/protostudy sequence defines how we learn it. Owned by /define-validation. Observable signals, interview instruments, and reflection protocols are developed per-MVP using /protostudy-prep. -->

This document provides the strategic overview of what we're validating, why, and in what order. It defines a series of protostudies to validate and derisk both the product and research aspects of the project. Detailed build plans, data collection instruments, and reflection protocols live in per-MVP protostudy documents.

---

## Core Hypotheses & Research Questions


What we're trying to learn, organized by categories that span our integrated approach — contextual understanding, product viability, design knowledge, and community impact. Each item concisely describes what the question/hypothesis is and why it matters to us. They will be fleshed out in more detail in the individual protostudy documents.

### Context: User & Ecosystem

Building a deeper understanding of the user and community ecosystem — surfacing insights about needs and contextual, systemic risks that shape what to design.

1. **H1: Scribe Erasure Dynamics** *(Open Question — MVP 1).* How do student and research teams currently experience minority voice erasure and dominant voice capture during the final plan drafting phase in meetings, and what visual references do they consult to resolve these conflicts?
2. **H2: Domain Conflict Nuances** *(Open Question — MVP 2).* How do different planning domains (academic spec/IRB prep vs. general/informal roadmap design) affect the types of structural layout and conceptual contradictions that teams find hardest to resolve?

### Value: Product-Market Fit, Demand & Growth

Does the product solve a felt need, and will people adopt and spread it? These questions determine whether the solution is viable as a sustained offering.

3. **H3: Meeting Efficiency Moat** *(Prediction — MVP 1).* If we provide system-generated Vision Templates and rating heatmaps, then teams will spend 50% fewer hours in sync meetings to reach alignment, because the visual representations offload the cognitive work of locating contradictions, bypassing unstructured verbal debates. *If wrong:* The coordination and synthesis overhead of the tool outweighs its benefit. *(Informs Impact: evidence of Distributed Cognition [Hutchins, 1995](https://doi.org/10.7551/mitpress/1881.001.0001) offloading coordination overhead — see HN.)*
4. **H4: Flexible Ingestion Appeal** *(Prediction + Open Question — MVP 2).* If we allow team members to upload drafts in any formatting style (narrative, bullets, templates), then initial workspace onboarding adoption will increase by 40%, because it removes formatting friction for individual contributors. *Open question:* How frequently will team members choose to write in the built-in editor versus dragging-and-dropping external markdown drafts?

### Design: Embodiment & Experience

How users interpret and interact with the design — the design conjectures and experiential insights that shape the next design iteration and design theory.

5. **H5: Visual Contrast Scaffolding** *(Prediction + Open Question — MVP 1).* If we present contrasting system-generated "Vision Templates" (Vision A vs. Vision B) as Boundary Objects, then teams will actively negotiate structural tradeoffs and define rules rather than defaulting to lazy, fragmented compromises, because the templates force them to visually confront incompatible choices. *Open question:* Will users attempt to bypass structural rule gates through raw text entry, or will they actively adopt the system's structural choices? *(Informs Design: testing Boundary Objects [Star & Griesemer, 1989](https://doi.org/10.1177/030631289019003001) in groupware.)*
6. **H6: Facilitator Tone & Compliance** *(Prediction + Open Question — MVP 2).* If we align the agent's facilitation tone with the active domain mode (rigorous for academic, casual for general), then prompt compliance (response rate to critiques) will increase by 25% and user irritation scores will drop, because the agent's authority matches the team's expectations. *Open question:* How do team members verbally discuss and respond to the agent's supportive critiques during sync meetings?

### Impact: Mediating Processes & Outcomes

The deeper psychological and behavioral changes we hope to produce — the theoretical conjectures and the actual community impact we're striving for.

7. **H7: Minority Voice Safeguards** *(Prediction — MVP 1).* If we display a Visual Integration Checklist and enforce a Consensus Approval Gate, then quiet team members will report a 30% higher rating of idea representation, because the interface makes un-integrated contributions visually salient to the entire team, reducing the scribe's social filtering. *If wrong:* Scribes will still dominate the narrative verbally during meetings, rendering the UI safety indicators ineffective. *(Informs Impact: testing Mattering Theory [Schlossberg] and Distributed Cognition [Hutchins, 1995](https://doi.org/10.7551/mitpress/1881.001.0001) safeguards.)*
8. **H8: Simulation Rationale Depth** *(Prediction — MVP 2).* If we force teams to engage with User Archetype Simulations using a gated dismiss release valve, then final project plans will address 30% more user research edge-cases than teams that skip or dismiss the simulation, because the gate prevents uncritical bypassing of safety warnings. *If wrong:* Persona simulations are viewed as a decorative chore rather than an active tool for expanding rationale.

---

## MVP / Protostudy Sequence

### Product Perspective

How can we build a web portal that reduces coordination overhead and structures synthesis without becoming a bloated collaborative document editor? The key product risks, in priority order:

1. **Collaborative Editor Overlap** — If users try to write their full drafts inside the tool rather than exporting aligned blocks to Google Docs/Notion, Co-Align will become a redundant editor, losing its focused niche and competing directly with incumbents.
2. **Clarification Interview Fatigue** — If the agent prompts users with too many clarification questions or rationale checkups during the silent brainstorming phase, users will abandon the workspace before the sync meeting even begins.

### Research Perspective

In group planning, is it better for AI to do the synthesis for the team, or is it better for the AI to highlight the differences and force the humans to negotiate them? The key research risks, in the order we need to verify them:

1. **Uncritical Acceptance of AI Synthesis** — If the AI-generated Vision Templates are too detailed, the group will uncritically adopt one rather than actively negotiating the structural tradeoffs.
2. **Scribe Dominance / Veto Friction** — Even with visual checklists and approval gates, dominant social pressure in sync meetings will lead quiet members to blindly click "Approve Synthesis" to avoid public conflict.

### Timeline

Deploy within our target community (Tech4Good research lab members and student course projects).

| Phase | Target Date | What Happens | What We Learn |
|---|---|---|---|
| **MVP 1: Contrasting Visions & Basic Safeguards** | Oct 15, 2026 | Deployed to 3 student course groups (3-5 members each) working on class proposals. They upload drafts, see contrasting visions, and draft final specs. | Can contrasting Vision Templates force tradeoff negotiation? Do checklists and approval gates protect quiet voice representation? (Addresses: H1, H3, H5, H7) |
| **MVP 2: Adaptive Facilitation & Simulation** | Nov 15, 2026 | Deployed to 3 research teams (academic specs) and 3 student teams (general planning). Includes the Dual Mode Toggle, simulator sandbox, and silent chat interview. | How does facilitation tone (Academic vs. Informal) affect team dynamics? Do simulations expand planning rationale depth? (Addresses: H2, H4, H6, H8) |

### MVP 1: Contrasting Visions & Basic Safeguards

**Purpose:** Verify that contrasting boundary objects (Vision Templates A vs. B) scaffold structural negotiation, and that visual anchors and approval gates prevent minority voice erasure during final scribing. *(Addresses: H1, H3, H5, H7)*

**What we build:** 
* A web portal where team members paste brainstorm notes or drag-and-drop markdown drafts.
* A dashboard that highlights structural contradictions and generates two contrasting visual Vision Templates (Vision A vs. B).
* A shared collaborative editor for the scribe with two read-only reference panels displaying original drafts, a red/green Visual Integration Checklist, and a Consensus Approval Gate button.

**How we learn:** 
We will deploy the portal to 3 student course groups. We will:
1. Log system interaction data (checking how long panels are viewed, checklist item status changes, and veto clicks).
2. Record and transcribe the sync meetings to run qualitative analysis on how teams discuss warnings and resolve contradictions.
3. Conduct post-meeting surveys of all participants comparing perceived idea representation with standard Google Docs meetings.

→ Detailed plan: *to be created via /protostudy-prep*

### MVP 2: Adaptive Facilitation & Simulation

**Purpose:** Validate if dual mode configuration (Academic vs. Informal) aligns the agent's authority with the group's domain, and whether persona simulations expand planning depth when bypass logic is gated. *(Addresses: H2, H4, H6, H8)*

**What we build:** 
* Workspace setup screen with the **Facilitation Mode Selection** toggle (Formal/Academic vs. General/Informal).
* A single-round clarification chat panel in the silent phase for missing rationales.
* The User Archetype Simulation sidebar panel with the **Gated "Dismiss" release valve** (hidden until the team types their first response to the simulator's critique).

**How we learn:** 
We will deploy the tool to 3 academic research groups and 3 general student planning groups. We will:
1. Measure prompt compliance and user engagement across the two toggle modes.
2. Log simulator interaction times, response length, and how often the gated "Dismiss" button is utilized.
3. Compare the number of user research edge-cases addressed in the final proposals between groups that engaged with the simulator vs. historical controls.

→ Detailed plan: *to be created via /protostudy-prep*

---

## Positionality Statement

[Positionality statement to be drafted and finalized in Step 3.]

---

## Appendix: Stances & Deferred Issues

### Core Hypotheses & Research Questions

### MVP / Protostudy Sequence
