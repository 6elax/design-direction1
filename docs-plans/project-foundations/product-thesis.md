# Co-Align Product Thesis

<!-- Target User & Need, Product & Value Proposition, and Unique Differentiation. Owned by /define-product -->

<!-- This section defines who the product is for, what it does, and why it needs to exist. It covers the target user, the core problem, the solution, and the unique value proposition. -->

## Target User & Need

### 1. Project Lead / Research Coordinator (Primary)
- **Target User:** A project lead, research coordinator, or team manager directing a collaborative group of 3–8 members (e.g., student project groups, research labs, or cross-functional startup teams).
- **Core Need:** To guide the team through making hard tradeoffs and aligning on a cohesive plan, without falling into the "compromise trap" (bloated, unfocused plans) or the "dominant voice trap" (where teammates feel ignored).
- **Insight:** Simply listing discussion questions doesn't help a team align—it just starts debates. Real alignment requires visualizing the consequences of choices. By presenting the team with contrasting cohesive visions (e.g., Vision A vs. Vision B) based on their divergent inputs, and letting them vote on elements to adjust weights, the lead can help the team converge on a single focused plan.
- **Status Quo:** They run long, unstructured meetings to debate divergent ideas, or they manually try to merge conflicting documents, ending up with a compromise draft that pleases no one and lacks product focus.
- **Demand Evidence:**
  - *Observed:* Team leads spend significant time in sync meetings just parsing "what did everyone do?" and trying to reconcile conflicting opinions.
  - *Hypothesized:* Teams spend more time negotiating differences and manually merging documents than actually refining their core ideas.
- **Must-Have User:** A group project leader in a design, engineering, or research course with 3–5 team members who must submit a single project proposal or design specification by a strict deadline.
  - *Why them specifically:* They have a hard deadline, are working with peers who all have divergent ideas, and have no formal authority to dictate the final plan.
  - *Access:* Tech4Good lab members or class projects.

### 2. Individual Contributor / Researcher (Secondary)
- **Target User:** An individual researcher, designer, or developer who brainstorms, writes notes, or drafts outlines independently in any style (bullet points, narratives, or structured templates).
- **Core Need:** To ensure their unique perspectives, reasoning, and ideas are accurately represented in the group's candidate proposal without being drowned out by more dominant teammates.
- **Insight:** People feel frustrated when they spend hours thinking and brainstorming, only for the group to adopt a completely different direction in a meeting without even discussing their alternative.
- **Status Quo:** Verbally pitching their ideas in a meeting or pasting their thoughts at the bottom of a shared Google Doc, hoping someone reads it.
- **Demand Evidence:**
  - *Observed:* Team members expressing frustration that "my ideas weren't even discussed in the meeting" or "we just went with the PM's draft."
  - *Hypothesized:* Contributors are more willing to yield on their ideas if they know they were explicitly considered and discussed.
- **Must-Have Customer:** An active individual contributor who goes deep in brainstorming and gets frustrated when their ideas are overlooked during group meetings.
  - *Why them specifically:* Lived experience of having great ideas that got lost in the noise of sync meetings.
  - *Access:* Tech4Good lab members or class projects.

## Product & Value Proposition
- **One-Liner:** Co-Align aggregates divergent team brainstorms, interviews members to extract their rationale, and generates contrasting candidate templates (e.g. following different core directions) with a weighted voting system to help the team align on hard tradeoffs.
- **Core Concept:** When team members brainstorm separately in any style, Co-Align extracts their key points. It identifies conflicts and interviews members to extract their underlying rationale. If two popular ideas contradict, it generates two distinct "Vision Templates" (Vision A vs. Vision B). Using a weighted voting system, the team can see how voting shifts the plan's configuration, helping them converge on a primary direction while integrating secondary ideas.
- **Core Experience:**
  1. The project leader sets up a shared workspace with a target planning template.
  2. Each team member brainstorms in their own style (unstructured, bullets, templates) and uploads their output.
  3. Co-Align extracts the key points and identifies gaps or conflicts. If a member's rationale isn't clear, the agent conducts a supportive, non-confrontational clarification chat to get follow-up reasoning.
  4. If popular ideas are contradictory, Co-Align generates two distinct "Vision Templates" representing the competing cohesive directions.
  5. During sync meetings, the team uses a weighted voting dashboard to vote on ideas/themes. The ideas with the most votes "consume" the main project definition, while less-voted ideas are integrated as secondary or supporting features.
  6. The team interacts with the candidates and vote distributions to finalize their aligned plan.
- **Value Proposition:**
  - *Narrative:* Co-Align makes team convergence engaging and structured. By conducting automated interviews for rationale, generating contrasting cohesive templates, and applying weighted votes, it helps teams avoid painful debates and construct a single, focused product plan that values everyone's contributions.
  - *Testable hypothesis:* Teams using Co-Align will reach alignment on a multi-dimensional planning document in 50% fewer meeting hours and with higher teammate satisfaction of their ideas being represented compared to teams using standard Google Docs/meetings.
- **Aha Moments:**
  - *Primary user (first aha):* When they run the synthesis and see two distinct, cohesive project templates representing the team's competing visions, rather than a giant list of unstructured comments.
  - *Primary user (sustained aha):* When the team uses the voting dashboard and sees the candidate template dynamically adapt to reflect the weighted votes, immediately highlighting the final plan structure.
  - *Secondary user/customer (first aha):* When the agent asks them supportive, clarifying questions about their ideas, making them feel their reasoning is valued before the group even meets.
- **Narrowest Wedge (MVP):**
  - *Included:* A web portal where team members can paste their brainstorm notes or drag-and-drop a markdown/text draft. It extracts key points, conducts a single-round clarification chat panel for missing rationales, and displays a basic split-screen voting interface showing the divergent options.
  - *Excluded (future expansion):* Git repo integration, Slack/Discord integrations, live multi-user cursor editing, real-time audio transcript synthesis.

## Interface & System Design

### 1. Concrete Form Factor & Workflows
Co-Align is **strictly a Web-based Portal** to ensure seamless accessibility for all cross-functional team members (designers, researchers, developers) without technical barriers (like Git):
- **Collaborative Project Workspace:** The team lead creates a project workspace URL (e.g. `co-align.app/workspace/project-xyz`) and invites the team.
- **Facilitation Mode Selection:** At project setup, the lead selects the workspace mode:
  - **Formal/Academic Mode:** Optimizes the agent for logical rigor, usability heuristics, academic templates (IRB, specs), and deep rationale checking.
  - **General/Informal Mode:** Optimizes the agent for speed, creative flexibility, general templates (marketing, event planning), and casual facilitation.
- **Individual Brainstorming Phase:** 
  - Members log in and draft their brainstorms directly in a built-in, distraction-free editor structured around the target template. Their personal AI brainstorming agent sits in a sidebar to help them outline and draft ideas.
  - Alternatively, members who prefer writing elsewhere (e.g., in VS Code, Google Docs, or Notion) can drag-and-drop their files (Markdown, TXT, Word) directly into the browser portal to upload their draft.
- **Session Database:** All submissions are saved to the project's central database (SQLite/PostgreSQL). The dashboard compares drafts and generates alignment playground assets.

### 2. Interaction Design: The 3-Phase Alignment Meeting
During the sync meeting, the team opens the Co-Align dashboard on a shared screen. The meeting proceeds in three structured phases:
- **Phase 1: Silent Review & Input (5–10 mins):** 
  - Members review the extracted ideas and contrasting proposals on their own devices.
  - They cast weighted scores (1–5) and type brief rationale. If a member has already provided rationale during their brainstorming stage, the system auto-populates it so they do not have to type it again.
- **Phase 2: Encouraging Discussion Heatmap (20 mins):** 
  - The shared dashboard shows a rating heatmap highlighting consensus points and rating gaps.
  - Rather than using confrontational prompts, the agent acts as a supportive facilitator. For example, instead of *"Alice, why did you score feasibility a 1?"*, it prompts: *"There are differing assumptions around the development time for Feature X. Let's discuss what challenges we might face."* The team lead can customize or live-edit the agent's prompt guidelines in the settings panel.
- **Phase 3: Interactive Decision & Scribing (10 mins):**
  - **Collaborative Editor with Scribe:** The final document editor is fully collaborative (like Google Docs)—any member can jump in to edit or tweak sections. However, the team designates one member as a "secretary/scribe" to take lead notes.
  - **Reference Side-Panels:** While editing, the original inputs typed by individual members during the quiet reflective phase are displayed in read-only side-panels, ensuring their original voices are never overwritten or forgotten.

### 3. Dialogue-Driven Simulation Sandbox
To resolve debates without the agent dictating the path, the dashboard includes a simulation playground:
- **User Archetype Simulations:** The agent simulates how diverse personas (e.g. *Impatient Ian*, *Power-user Pam*) would react to the current plan. In **General Mode**, the personas are casual; in **Academic Mode**, they focus heavily on user research criteria and academic specs.
- **Bi-Directional Feedback Loop:** If the agent flags a concern (e.g. *"Ian will get stuck here because X"*), it must state its exact reasoning based on usability heuristics. If the team disagrees, they must type their rationale to correct/convince the agent.
- **Gated "Dismiss" Release Valve:** To prevent users from immediately skipping the validation step, the **"Dismiss / Accept Risk"** button is hidden initially. It only appears *after* the team has made their first attempt to type a response/justification to the agent's concern. If the agent continues to push back after their response, they can click "Dismiss" to override the warning and proceed.

### 4. Gatekeeper for Contradictory Merges
When the team attempts to merge mutually exclusive features, the agent acts as a structural gatekeeper:
- If Bob votes for "Vision A (Dark/Minimal)" and Alice votes for "Vision B (Bright/Dense Layout)", a naive merge is blocked.
- The agent prompts: *"You are merging two incompatible layouts. To proceed, please clarify: (1) Will this support a toggle between Light and Dark mode? (2) Which layout structure (Minimal vs. Dense Grid) should be the core layout?"* The merge is only executed once the team clarifies the structural rules.

## Unique Differentiation
- **Structural Advantages:**
  - *Founder Advantage:* Lived experience in the Tech4Good research lab where collaborative planning is frequent and AI agents are integrated into the workflow.
  - *Market Advantage:* The explosion of individual AI assistant usage creates a massive amount of divergent drafts. No existing tools focus on multi-agent synthesis for team alignment.
  - *Product Advantage:* Direct semantic mapping of parallel document structures (templates, markdown outlines) that standard collaboration tools (like Figma/Slack) do not capture.
  - *Acquisition Advantage:* Tech4Good lab and class networks can adopt this immediately for group projects.
  - *Academic & Design Domain Focus:* Unlike general-purpose tools, Co-Align optimizes for specific academic and project design templates (e.g. IRB, CHI Concept papers, engineering specs). The more teams use these templates, the better our models become at understanding domain-specific constraints.
- **Hard Tradeoffs:**
  - *Not a live document editor:* We are not trying to replace Google Docs or Notion for writing the actual project text. Co-Align is strictly a synthesis, voting, and conflict-resolution sandbox. Once alignment is reached on the conflicting blocks, the secretary exports/copies the consolidated draft into the team's primary document (Notion/Google Docs) to finish writing.
  - *Text-first workflow first:* Focusing entirely on markdown files and structured text templates, rather than audio transcriptions or whiteboards.
- **Sustainability & Moat:**
  - *Why incumbents can't easily copy:* Incumbents (Google Docs, Notion) focus on real-time synchronous typing and generic commercial summaries. They do not design specialized workflows for pedagogical alignment (e.g. consensus safety, non-judgmental student facilitation, and specific academic proposal constraints).
- **Future-Fit Thesis:** As agents become more autonomous and personal, every human will have their own agent. The primary bottleneck in organizations will shift from individual productivity to agent-mediated group alignment. Co-Align is built for this future.
- **Comparative Positioning:**
  - *vs. Google Docs:* Google Docs is a blank slate; it does not help you reconcile conflicting text or generate structured meeting agendas from separate edits.
  - *vs. Notion AI:* Notion AI can summarize a single page, but it doesn't aggregate multiple divergent pages from different users to find contradictions and construct a synthesis, nor does it specialize in academic templates.
  - *vs. Slack:* Slack is transactional and ephemeral; discussions are unstructured and easily lost.
- **Pricing Model:** Open source / Free for academic and small teams; subscription for team collaboration features.

## Appendix: Product Definition
<!-- Stances & Open Issues from the definition process. Owned by /define-product.
     Log ONLY:
     - 🔵 Strong Stances: moments where the user pushed back against something the agent proposed and explained their reasoning. Must state what was rejected and why.
     - ⏳ Deferred Issues: questions, concerns, or scope decisions explicitly flagged to revisit later.
     Do NOT log decisions that have been fully incorporated into the main body — the main body should already make the case.
     The full cycle-by-cycle evolution is tracked in product-thesis-evolution.md. -->

### Target User & Need
- 🔵 **Strong Stance on Agent Constraint**: The user clarified that the project does not need to specifically ingest agentic chat logs. The core problem is the general team alignment challenge of converging divergent individual ideas from a brainstorming phase into a single plan. The product should focus on aggregating brainstormed outputs (of any kind, such as templates or notes) to identify discussion points and generate a candidate template to help the group converge.
- 🔵 **Strong Stance on Alignment Method**: The user rejected the idea of just generating discussion questions as too "boring." Instead, they proposed that the agent should: (1) interview members to extract their rationale; (2) extract key points regardless of writing style; (3) generate multiple candidate templates (e.g., following compromise or dominant voice traps, or contrasting visions) if ideas conflict, enabling the team to run a weighted vote to merge or select their final direction.

### Product & Value Proposition
- 🔵 **Strong Stance on Agent Decision-Making:** The user emphasized that the agent must never make decisions or dictate the final plan. The human team members are the ultimate owners. The agent's role is strictly to visualize alternatives, point out contradictions, facilitate dialogues, and request specific human-defined merging rules when incompatible choices are combined.
- 🔵 **Strong Stance on Facilitator Tone & Pressure:** The user pushed back against direct, confrontational questions like "Alice, why did you score feasibility low?" which feel intimidating and may cause team members to shut down. The agent's prompts must be non-judgmental, focus on high-level goals, and be customizable by the team lead.
- 🔵 **Strong Stance on Input Redundancy:** The user stated that if a user has already written an explanation for their score or idea, the agent must reuse that text rather than asking them to repeat or explain it again.
- 🔵 **Strong Stance on Collaborative Scribing:** The user specified that the final editor must be collaborative (anyone can edit or tweak), but one secretary/scribe takes the lead in writing notes. Individual original ideas are preserved as read-only references in side-panels to prevent them from being lost.
- 🔵 **Strong Stance on Bypassing Simulation (Gated Dismissal):** The user specified that the "Dismiss / Accept Risk" option must only appear *after* the team has made their first attempt to respond/justify their choice to the simulator, preventing them from skipping the validation step immediately.
- 🔵 **Strong Stance on Strictly Web Platform:** The user pushed to consolidate the platform to a single interface to avoid confusion. The team chose a purely web-based portal over Git branch syncing because it is accessible to all cross-functional roles (designers, researchers, developers) without technical barriers.

### Unique Differentiation
- 🔵 **Strong Stance on Non-Editor Boundary:** The team solidified that Co-Align is not a live writing document editor like Google Docs or Notion. It is strictly a synthesis, voting, and sandbox options-resolver that exports the finalized plan, keeping the scope focused and preventing competitive dilution with incumbents.
- 🔵 **Strong Stance on Domain Specialization (Moat):** Aligned that Co-Align's core moat is domain specialization in academic and design templates (IRB, specs, CHI draft papers) and non-judgmental facilitation, which general-purpose tools like Notion AI or Google Docs will never target.
- 🔵 **Strong Stance on System Flexibility (Formal vs. Informal Modes):** The user rejected locking the tool strictly to academic templates. They specified that the tool should be flexible enough to support both formal/academic settings and informal/general planning. To make this work, the agent will ask the team at project setup whether their project is "Formal/Academic" or "General/Informal," allowing the system to adjust its facilitation tone, simulator personas, and rationale checking depth accordingly.
