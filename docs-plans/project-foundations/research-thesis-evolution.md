# Document Evolution Log — Co-Align Research Landscape

<!-- A structured record of how the Research Landscape section of product-thesis.md evolved through the planning session.
     Each cycle captures the interaction between human and AI that produced a change
     in the document. User input is always quoted verbatim.

     This file is built in two phases:
     - Phase 1 (during session): Cycle records are appended after each critique-respond-update turn.
     - Phase 2 (end of session): Summary Statistics and Evolution by Section are generated. -->

---

## Cycle 1: Initial Draft

### User Input
> i'm not very sure about what research contributions already exist. do you have ideas of what exist, and how this can be considered a unique research contribution? also please make a new file for research thesis

### AI Draft Summary
Generated the initial draft at `docs-plans/project-foundations/research-thesis.md` based on the product definition:
1. **Relevant Research Threads:** Identified three conversations: (1) Divergence & Convergence in Collaborative Writing (CSCW), (2) Pedagogical Scripting and Agency in Group Coordination (CSCL), and (3) Mixed-Initiative AI in Group Decision Facilitation.
2. **Theory Recommendations:** Recommended Distributed Cognition (Hutchins) to ground the sync meeting workspace, and Boundary Objects (Star & Griesemer) to ground the generated contrasting "Vision Templates." 
3. **Gaps & Opportunities:** Formulated two gaps: (1) Reconciling divergence without Frankenstein merges (structural contradictions), and (2) Gating persona simulation bias (mitigating confirmation bias with gated overrides).
4. **Knowledge Contribution Framing:** Framed the bit flip: most systems assume AI should automatically generate a single optimized consensus synthesis; our work shows AI is more effective when it highlights contradictions, generates contrasting visions, and forces humans to negotiate the tradeoffs. Targeted CSCW/CHI.

### What the AI added beyond what the user said
- Selected and articulated specific CSCW, CSCL, and Mixed-Initiative threads, grounding them in established literature (Lowry et al., 2004; Bannon & Bødker, 1997; Dillenbourg, 2002; Kobbe et al., 2007; Horvitz, 1999; Hancock et al., 2020).
- Proposed Distributed Cognition and Boundary Objects as a coherent theoretical chain (problem -> mechanism -> outcome).
- Formulated knowledge gaps (non-cohesive merges, simulation confirmation bias) mapping directly to the product's interface design choices (merge gatekeeper, gated dismiss valve).
- Framed the academic contribution separate from the product's value proposition, defining a distinct "bit flip" and novelty defense against standard LLM summarization.

---

## Cycle 2: Focus on Trade-off Visualizations and Minority Voice Preservation

### User Input
> I like question 1. question 2 seems not very relevant to what we're trying to do with this project. for question 3, i don't see how stimulating "user personas" helps with "finding and interviewing" real users. 
> so it seems question 1 is the best so far.

### AI Critique
None; the user selected the primary negotiation thread and pushed back on scripting/personas as irrelevant.

### Document Delta
| Field | Before | After |
| :--- | :--- | :--- |
| **Relevant Research Threads** | Thread 1: CSCW Gaps. Thread 2: CSCL scripting. Thread 3: Mixed-initiative AI. | Thread 1: Visualizing Trade-offs vs. Automating Synthesis in Groupware (CSCW). Thread 2: Consensus Safety and Minority Voice Preservation in CSCW. Removed pedagogical scripting and user persona simulator threads. |
| **Gaps & Opportunities** | Gap 1: Reconciling Divergence. Gap 2: Gating Persona Simulation. | Gap 1: Reconciling Divergence without Frankenstein merges. Gap 2: Preventing Minority Voice Erasure during Groupware Convergence. Removed simulator override gap. |

### What shifted
- Narrowed research scope to focus strictly on CSCW groupware dynamics. Removed the pedagogical learning-sciences scripting and user persona simulation threads based on user feedback. Recentered the secondary thread on consensus safety and minority voice preservation.

---

## Cycle 3: Integrating Direct Research Questions and Designing Minority Safeguards

### User Input
> what happened to the idea of question 1 with the research question, "In group planning, is it better for AI to do the synthesis for the team, or is it better for the AI to highlight the differences and force the humans to negotiate them?" ?
> 
> deep grills:
> 1. i think the system design will warn them? and after the warning, the users can choose to continue or not, but the users should have the context of what happens if they continue, or maybe reasons they shouldnt continue. i think having users define structural rules is fine, and then being strict about choices/designs visualized based on those rules.
> 2. to be honest i'm not very sure, can you give more ideas for how people's ideas can be protected from dominant members?

### AI Critique
None; updated the document to restore the user's exact research question wording and brainstormed specific UI mechanisms for minority voice protection.

### Document Delta
| Field | Before | After |
| :--- | :--- | :--- |
| **Relevant Research Threads** | Open Tensions: generic CSCW synthesis question. | Updated Tension 1 with the user's exact wording: "In group planning, is it better for AI to do the synthesis for the team, or is it better for the AI to highlight the differences and force the humans to negotiate them?" |
| **Gaps & Opportunities** | Gap 2: Anchoring ideas in side-panels. | Expanded Gap 2 to include visual checklists of quiet members' ideas, asynchronous approval gates, and logging rejection rationales. |

### What shifted
- Restored the user's exact, clear research question to Thread 1. Expanded the research gap design on minority voice preservation to incorporate three specific safety mechanisms: visual integration tracking, approval/veto gates, and logged rejection archives.

---

## Cycle 4: Deferring Gap Evaluation Metrics to Validation Phase

### User Input
> for the grills you have, i'm not very sure for the answer. maybe we can keep this in the back of our minds (log this somewhere) and come back to it as a question for the future as we test things out with protostudy? i currently have no idea how to measure/study these behaviors (unless you have ideas)

### AI Critique
None; aligned on logging evaluation metrics for Gap 1 and Gap 2 as deferred issues to address during the validation planning phase.

### Document Delta
| Field | Before | After |
| :--- | :--- | :--- |
| **Appendix: Gaps & Opportunities** | Empty | Added deferred issues for measuring warning effectiveness (Gap 1) and evaluation metrics for minority preservation (Gap 2). |

### What shifted
- Logged gap evaluation metrics as deferred issues in the Appendix, resolving structural questions on how to measure group dynamics and consensus safety by postponing them to the upcoming validation and protostudy scoping phase.

---

<!-- Append one cycle per critique-respond-update turn. Use continuous numbering across all sections. -->
