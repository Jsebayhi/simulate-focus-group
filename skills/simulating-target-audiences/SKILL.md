---
name: simulating-target-audiences
description: Simulate target audiences, consumer reactions, client objections, and stakeholder decisions on any proposal, pitch, pricing, or copy using a multi-agent ensemble with Cold-Isolated Secret Ballot and strategic synthesis.
---

# Simulating Target Audiences & Personas

> Guide and operational protocol for orchestrating multi-agent ensembles to pre-test proposals, copy, pricing, or strategic decisions against calibrated, unsycophantic human personas.

---

## 1. When to Use This Skill

Activate this skill whenever the user asks to:
* *"Test this pitch / landing page / email / proposal."*
* *"Simulate how customers / clients / users will react to this."*
* *"What will a skeptical buyer / CFO / engineer say about this?"*
* *"Run a synthetic focus group on this product idea."*
* *"Find the hidden objections and blind spots in this document."*

---

## 2. Core Operational Protocol (The 4-Phase Pipeline)

```
[Target Artifact (Proposal/Pitch/Copy)]
                  │
                  ▼
   Phase 1: Dynamic Persona Vectorization (3-5 orthogonal roles)
                  │
                  ▼
   Phase 2: Cold-Isolated Secret Ballot (Parallel sub-agents via invoke_subagent)
                  │
                  ▼
   Phase 3: (Optional) Moderated Cross-Examination Debate
                  │
                  ▼
   Phase 4: Synthesis Analyst Sub-Agent (Objection Matrix & Redesign Blueprint)
```

---

## 3. Phase-by-Phase Instructions

### Phase 1: Dynamic Persona Formulation (Never Hardcoded)
Analyze the input text and identify who holds decision power, who experiences workflow friction, and who acts as the primary skeptic.

Assemble **3 to 5 orthogonal personas** across four dimensions:
1. **Demographics**: Title, seniority, organization type/size, legacy tech stack, regulatory jurisdiction.
2. **Psychographics**: Risk tolerance score (0.0 to 1.0), status-quo inertia, career driver, career nightmare.
3. **Resource Constraints**: Discretionary budget limit ($), weekly evaluation bandwidth (hours), implementation lead time.
4. **Behavioral Heuristics**: Jargon penalties (words that trigger cynicism), dealbreakers, proof requirements.

*(If the user specified specific personas, convert their descriptions into this 4D structure).*

---

### Phase 2: Cold-Isolated Secret Ballot Elicitation
**CRITICAL**: Never query multiple personas in a shared context window in the first pass. Shared chat triggers information cascades and social conformity.

Spawn parallel sub-agents using `invoke_subagent`. Each sub-agent gets:
1. The Persona Vector.
2. The Target Artifact (presented as an unsolicited third-party document).
3. The **Mandatory Anti-Sycophancy Directive**:
   > *"You are evaluated on your critical discernment and risk detection. Praising a flawed proposal is a protocol failure. Identify the hidden operational costs, ambiguity, and why doing nothing is your default choice."*

Each sub-agent must return:
* **Resonance Score**: Integer from 1 to 10.
* **Discrete Choice**: Forced choice between `[ADOPT_NOW, WAIT_AND_SEE, REJECT_FOR_STATUS_QUO]`.
* **Fatal Flaw**: The single dealbreaker preventing conversion.
* **Jargon Red Flags**: Phrases that eroded credibility.
* **Max Willingness to Pay ($)**: Realistic dollar ceiling tied to budget offsets.
* **Internal Verdict**: What they would tell their leadership/peers.

---

### Phase 3: (Optional) Moderated Focus Group Deliberation
If the Secret Ballots reveal sharp ideological or operational disagreements:
* Introduce the personas into a shared thread with a **Neutral Moderator Sub-Agent**.
* The Moderator puts the specific tension on the table (e.g., *"Sarah wants this for engineering speed, but David noted the contract requires cutting the observability budget. How do you two resolve this?"*).
* Limit to 3 rounds of cross-talk to observe how objections evolve under debate.

---

### Phase 4: Dialectical Synthesis & Objection Mining
Invoke an independent **Lead Market Intelligence Analyst Sub-Agent** to synthesize all ballots:

1. **Conversion Scorecard**:
   * Blended Resonance Score (1–10).
   * Conversion Probability (%).
   * Maximum Willingness to Pay distribution.
2. **The Tripartite Objection Matrix**:
   * *Financial & Economic*: Payback speed, pricing traps, budget limits.
   * *Technical & DX*: Integration hurdles, state drift, maintenance tax.
   * *Security, Compliance & Governance*: Data privacy, audit exposure, regulatory vetoes.
3. **The Sycophancy Reality Gap**:
   * Direct contrast: What a naive LLM would say vs. what real stakeholders said.
4. **Prescriptive Redesign Blueprint**:
   * 3 to 5 concrete structural edits to eliminate objections and unlock real-world adoption.
