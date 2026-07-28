# Co-Align Research Thesis

<!-- Relevant Research Threads, Theory Recommendations, Gaps & Opportunities, and Knowledge Contribution Framing. Owned by /define-research -->

*Deep literature review and Related Work preparation: see [research-thesis-prompt.md](./research-thesis-prompt.md).*

## Relevant Research Threads

### 1. Visualizing Trade-offs vs. Automating Synthesis in Groupware (CSCW)
- **Core Tension:** Scaffolding human negotiation vs. Automating consensus. Modern AI-assisted groupware systems focus heavily on automated synthesis—acting as an "AI secretary" that automatically merges team members' divergent inputs into a single summary. However, this automation reduces human cognitive engagement, leading to uncritical acceptance of the AI's compromises. Conversely, manual negotiation in standard groupware (like Google Docs or Notion comments) creates high "synthesis tax" and coordination overhead.
- **What the field knows:** Research in collaborative writing shows that structured templates reduce cognitive load and facilitate coordination ([Lowry et al., 2004](https://doi.org/10.1109/TPC.2004.825943)), and common information spaces help teams align on shared goals ([Bannon & Bødker, 1997](https://doi.org/10.1007/978-94-015-7372-6_6)). However, groupware has historically relied on manual text collation or simplistic voting (e.g., dot voting) to resolve structural conflicts, rather than representing conflicting conceptual visions.
- **Open Tensions:** In group planning, is it better for AI to do the synthesis for the team, or is it better for the AI to highlight the differences and force the humans to negotiate them? How can system-generated boundary objects (such as contrasting cohesive plan drafts representing competing directions) help teams visually negotiate conceptual tradeoffs (e.g. incompatible layout choices) without the AI overstepping human decision-making or producing fragmented, non-cohesive plans?

### 2. Consensus Safety and Minority Voice Preservation in Collaborative Design
- **Core Tension:** Preventing minority voice erasure vs. Group convergence. During team convergence, groups frequently fall into the *dominant voice trap* (where the loudest or most persuasive member's ideas override others) or the *compromise trap* (where ideas are diluted to satisfy everyone, destroying plan focus). 
- **What the field knows:** Collaborative design research shows that group dynamics naturally favor dominant voices, and minority opinions are frequently filtered out. While parallel writing and anonymous input features (like in brainstorming systems) protect early-stage contribution, these contributions are typically lost or overwritten when the group begins the final convergence and drafting phase.
- **Open Tensions:** How can groupware interfaces preserve consensus safety and prevent the erasure of minority views during the final editing phase (e.g., through visual integration checklists, veto approval gates, and logged rejection archives)?

## Theory Recommendations

### 1. Distributed Cognition (Hutchins) — *For the Sync Meeting Workspace*
- **Why this theory, specifically:** Distributed Cognition (DCog) predicts that cognitive processes are distributed across members, time, and external representations. Co-Align represents a distributed cognitive system: individual brainstorms are "external cognitive representations" that the AI aggregates and transforms into a consensus heatmap and contrasting "Vision Templates." By interacting with these artifacts, the group coordinates its decision-making, offloading the cognitive synthesis tax to the tool's interface.
- **Key reference:** [Hutchins, 1995](https://doi.org/10.7551/mitpress/1881.001.0001) — *Cognition in the Wild*. MIT Press.
- **Alternative considered:** Transactive Memory Systems ([Wegner, 1987](https://doi.org/10.1007/978-1-4612-4634-3_9)) was considered but rejected because TMS focuses on *who* knows *what*, whereas DCog explains *how* external cognitive representations are manipulated by physical artifacts to coordinate group problem-solving.

### 2. Boundary Objects (Star & Griesemer) — *For the Contrasting Vision Templates*
- **Why this theory, specifically:** Boundary Objects are artifacts that are flexible enough to adapt to local needs, yet robust enough to maintain a common identity across different social worlds. Our contrasting "Vision Templates" act as boundary objects: they allow team members with divergent perspectives (e.g., developer tech specs vs. designer layout wireframes) to align on high-level tradeoffs without needing a single, uniform view.
- **Key reference:** [Star & Griesemer, 1989](https://doi.org/10.1177/030631289019003001) — "Institutional Ecology, 'Translations' and Boundary Objects: Amateurs and Professionals in Berkeley's Museum of Vertebrate Zoology, 1907-39." *Social Studies of Science*, 19(3), 387-420.
- **Alternative considered:** Coordination Mechanisms ([Schmidt & Wagner, 2004](https://doi.org/10.1007/s10606-004-5059-3)) was rejected because it focuses on formal protocols for scheduling resources, whereas Boundary Objects explains how divergent conceptual views are negotiated.

**How the theories work together:**
These two theories form a coherent chain. **Distributed Cognition** explains the mechanism of how Co-Align aggregates and transforms individual inputs (independent drafts) into structured external representations (consensus heatmaps, interactive options). These representations then function as **Boundary Objects**, providing the shared, flexible artifacts that diverse team members interact with to negotiate tradeoffs and converge on a single plan.

### Theories to explore further
- **Mattering Theory (Schlossberg):** To investigate how preserving individual brainstorms in read-only reference panels affects team members' feeling of being "noticed" and valued during high-pressure sync meetings.
- **Conversational Grounding (Clark & Brennan):** To examine how the consensus safety features establish mutual evidence of understanding between dominant and quiet team members.

## Gaps & Opportunities

**How the research threads converge:**
Thread 1 (CSCW) establishes that standard groupware lacks mechanisms to resolve divergent text without manual synthesis tax or automated consensus bias. Thread 2 (Consensus Safety) reveals that minority opinions are easily erased when the group transitions from parallel brainstorming to final drafting.

**The overarching gap:**
HCI and collaborative design tools fail to support group convergence on complex plans in a way that preserves consensus safety and prevents the erasure of quiet voices. Prior systems either treat AI as an autonomous secretary (which automates consensus and reduces engagement) or a passive text editor. No system investigates how AI can act as a **tradeoff-representing facilitation mediator** that generates boundary objects (contrasting cohesive templates) and structures consensus-safe workspaces (with read-only reference side-panels) to help teams negotiate tradeoffs without taking away human decision-making or erasing quiet voices.

### Gap 1: Reconciling Divergence Without Frankenstein Merges (from Thread 1)
- **The gap:** The field does not know how to group, contrast, and negotiate structural contradictions in collaborative design documents without either defaulting to simple voting (which yields fragmented, non-cohesive plans) or letting the AI make the merge decisions.
- **Why this project fills it:** Co-Align takes a unique design position: it extracts semantic points, warns users when they attempt to merge contradictory structures (explaining the consequences and context of proceeding), but lets them choose. If they proceed, the system enforces the structural rules they defined and strictly visualizes options based on those rules.
- **Design knowledge generated:** How mixed-initiative tools can support structural convergence by forcing rule definition for contradictions rather than automating the merge.
- **How we'd observe this:** We will observe qualitative transcript data from team sync meetings to see how teams resolve blocked merges, and evaluate the final design coherence.

### Gap 2: Preventing Minority Voice Erasure in Groupware Synthesis (from Thread 2)
- **The gap:** How to prevent minority opinions and quiet members' ideas from being filtered out or overwritten when a team transitions from individual brainstorming to collaborative drafting under a scribe.
- **Why this project fills it:** We design a collaborative workspace that combines a shared editor with persistent, read-only side-panels that include: (1) a co-uptake checklist (highlighting points in red until the scribe integrates or references them); (2) a consensus approval gate (requiring all members to click approve on their own devices before exporting); and (3) a logged rejection archive (forcing the scribe to write why an idea was excluded rather than silently erasing it).
- **Design knowledge generated:** How persistent visual anchoring and consensus gates affect minority voice preservation and team member satisfaction during collaborative convergence.
- **How we'd observe this:** We will track system interaction logs (e.g., how often side-panels are viewed or quoted in edits) and run post-meeting surveys comparing team member satisfaction of idea representation.

## Knowledge Contribution Framing

*Note: The statements below are contribution hypotheses — framed as the potential claims we believe the eventual paper will be able to make, based on the gaps identified above. They will be refined or revised once deployment data confirms or challenges them.*

- **Knowledge Contribution (one sentence):** This work contributes design knowledge on how mixed-initiative systems can facilitate group convergence on complex plans by representing structural tradeoffs through contrasting cohesive templates and preserving consensus safety through persistent individual reference anchors.
- **Product Value vs. Research Contribution:** The product value is that teams reach alignment faster and feel more satisfied with their ideas. The research contribution is design knowledge about how tradeoff-representing visualizations and consensus-safe interface designs coordinate human decision-making and prevent minority voice erasure.
- **Bit Flip:** Most systems assume that AI should help groups reach alignment by automatically generating a single, optimized consensus synthesis. Our work shows that AI is more effective when it highlights structural contradictions, generates contrasting cohesive visions, and forces humans to negotiate the tradeoffs themselves—which not only builds shared ownership and deeper team learning, but also allows humans to co-construct novel perspectives and creative directions that an LLM cannot generate.
- **Novelty Defense:** Reviewer: "This is just applying LLM summaries to Google Docs." Response: "Google Docs summaries are static text reduction. Co-Align is a structured, mixed-initiative facilitation script that models decision tradeoffs, blocks incoherent merges, and preserves minority voices through persistent visual side-panels. Furthermore, it treats human negotiation not as an efficiency bottleneck to automate, but as a site of creative co-construction where humans produce unpredictable perspectives that AI synthesis cannot replicate."
- **Paper Type:** Systems paper with a deployment study.
- **Target Venue:** CSCW (primary) / CHI (secondary).
- **Audience:** Researchers in computer-supported cooperative work, collaborative writing, and mixed-initiative systems.

## Appendix: Research Landscape
<!-- Stances & Open Issues from the research landscape process. Owned by /define-research.
     Log ONLY:
     - 🔵 Strong Stances: moments where the user pushed back against something the agent proposed and explained their reasoning. Must state what was rejected and why.
     - ⏳ Deferred Issues: theories to revisit, citation gaps to verify, or scope decisions to reconsider.
     Do NOT log decisions that have been fully incorporated into the main body. -->

### Research Threads

### Theory Recommendations

### Gaps & Opportunities
- ⏳ **Deferred Issue: Measuring Warning Effectiveness (Gap 1):** Revisit how to measure whether structural contradiction warnings spark creative debate or simply lead to users picking a default choice to end the meeting. Needs to be evaluated during the protostudy/validation phase.
- ⏳ **Deferred Issue: Evaluation Metrics for Minority Preservation (Gap 2):** Revisit how to evaluate if consensus safety features (checklists, veto buttons, logged rejections) actually prevent idea erasure. Needs to be evaluated during the protostudy/validation phase (e.g. tracking checklist completion, veto click counts, and post-meeting satisfaction surveys).

### Knowledge Contribution Framing
