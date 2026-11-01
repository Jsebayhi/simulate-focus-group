# Theoretical Provenance & Skill Design Architecture

> The definitive engineering record documenting how scientific papers in computational social science, behavioral economics, and AI alignment were synthesized into the Target Audience Simulator skill, and how to upgrade it as new research emerges.

---

## 1. Executive Philosophy: The Synthesis Imperative

Most AI persona implementations fail because they rely on single-prompt intuition (e.g., *"Act as a 45-year-old CFO and critique this pitch"*). This causes two catastrophic failure modes:
* **The Sycophancy Trap**: Models trained via RLHF default to politeness and agreeable flattery.
* **The Caricature Trap**: Models without explicit economic constraints reduce complex human roles to shallow cartoon stereotypes.

The **Target Audience Simulator** skill was not invented from thin air. It is a systematic **engineering synthesis** uniting isolated breakthroughs from distinct scientific literature:
* Computational political science (*Algorithmic Fidelity*).
* Nobel-prize microeconomics (*Random Utility Theory & Discrete Choice*).
* Behavioral economics (*Homo Silicus, Loss Aversion, Status-Quo Bias*).
* AI alignment and red-teaming (*RLHF Sycophancy Inversion*).
* Information diffusion theory (*Multi-Agent Information Cascades*).

---

## 2. Paper-by-Paper Provenance: What Came From Where

```
                         THE SCIENTIFIC SYNTHESIS TREE
                         
      Argyle et al. (2023)              Aher et al. (2022) / Kahneman
      [Algorithmic Fidelity]            [Cognitive Biases & Loss Aversion]
               │                                      │
               ▼                                      ▼
      Dimension 1: Demographics              Dimension 2: Psychographics
      ─────────────────────────              ───────────────────────────
      Role, Seniority, Tech Stack,           Risk Tolerance (0-1), Inertia,
      Regulatory Jurisdictions               Loss Aversion (2.25x Multiplier)
               │                                      │
               └───────────────────┬──────────────────┘
                                   │
                                   ▼
                       [ 4D PERSONA STATE VECTOR ]
                                   ▲
               ┌───────────────────┴──────────────────┐
               │                                      │
      Dimension 3: Constraints               Dimension 4: Heuristics
      ────────────────────────               ───────────────────────
      Discretionary Budget Cap,              Fatal Flaw Mandate, Jargon
      Time & Implementation Lead             Penalties, Status Quo Default
               ▲                                      ▲
               │                                      │
      Horton et al. (2023) / Brand (2024)    Perez (2022) / Sharma (2023)
      [Homo Silicus & Discrete Choice]       [Sycophancy Mitigation & Inversion]
```

---

### Component 1: Dimension 1 (Demographics & Context)
* **Academic Source**: Lisa P. Argyle et al. (2023), *"Out of One, Many: Using Language Models to Simulate Human Samples"* (*Political Analysis*, Cambridge University Press).
* **The Provenance**: Argyle et al. proved that conditioning LLMs on census-grade, multi-attribute backstories shifts the token probability distribution from the generic corpus mean into the specific conditional sub-manifold of that demographic group, preserving real-world non-linear correlations across human attitudes.
* **Engineering Translation**: We formalized this into the `demographics` module of our YAML schema: title, seniority, organization type, headcount, current tech stack, and governing regulatory regimes (SOC2, HIPAA, GDPR).

---

### Component 2: Dimension 2 (Psychographics & Cognitive Biases)
* **Academic Source**: Gati Aher, Rosa Arriaga, & Adam Tauman Kalai (2022), *"Using Large Language Models to Simulate Multiple Humans and Replicate Human Subject Studies"* (*Microsoft Research / Georgia Tech*); Daniel Kahneman & Amos Tversky (1979), *"Prospect Theory: An Analysis of Decision under Risk"*.
* **The Provenance**: Aher et al. discovered that LLMs can accurately replicate human behavioral economics experiments (framing effects, ultimatum games, risk aversion), but only if the prompt explicitly provides the cognitive framing. Without it, models act unrealistically risk-neutral.
* **Engineering Translation**: We embedded numerical psychographic anchors:
  * `risk_tolerance`: Float from 0.0 (extreme paranoia) to 1.0 (risk seeker).
  * `status_quo_inertia`: Float from 0.0 to 1.0.
  * `loss_aversion_factor`: Multiplier (default human baseline 2.25–3.5) ensuring potential risks outweigh potential gains.
  * `career_driver` and `career_nightmare`: The explicit personal upside/downside balancing the decision.

---

### Component 3: Dimension 3 (Resource & Budget Constraints)
* **Academic Source**: John J. Horton, Apostolos Filippas, & Benjamin S. Manning (2023), *"Large Language Models as Simulated Economic Agents: What Can We Learn from Homo Silicus?"* (*NBER / MIT*); Daniel McFadden (1974), *"Conditional Logit Analysis of Qualitative Choice Behavior"*.
* **The Provenance**: Horton established that artificial economic actors ("Homo Silicus") behave consistently with microeconomic choice theory **only when bound by budget constraints**. In economics, an unconstrained agent will approve everything because words are costless ("cheap talk").
* **Engineering Translation**: We introduced the `constraints` module:
  * `discretionary_budget_usd`: Hard financial ceiling the persona can authorize without board escalation.
  * `evaluation_bandwidth_hours_per_week`: The persona's finite cognitive capacity.
  * `implementation_lead_time_months`: Operational friction for migrations.

---

### Component 4: Dimension 4 (Behavioral Heuristics & Anti-Sycophancy)
* **Academic Source**: Ethan Perez et al. (2022), *"Discovering Language Model Behaviors with Model-Written Evaluations"* (*Anthropic*); Mrinank Sharma et al. (2023), *"Towards Understanding Sycophancy in Language Models"* (*Anthropic / Oxford*); Kim Tae Jin et al. (2026), *"A Scalable Framework for Building Knowledge-Driven Synthetic Consumer Agents"* (*J. Ind. Inf. Integration*).
* **The Provenance**: Perez and Sharma proved that RLHF fine-tuning induces systemic sycophancy: models flatter users and affirm flawed pitches. Kim et al. proved that industrial synthetic agents require negative behavioral rules to prevent false validation.
* **Engineering Translation**: We built the **Anti-Sycophancy Inversion**:
  * *Third-Party Stimulus Framing*: Presenting the pitch as an unsolicited cold document from an unknown vendor.
  * *Fatal Flaw Mandate*: The agent is structurally required to identify the primary failure mode before emitting any positive evaluation.
  * `jargon_penalties`: Explicit list of marketing buzzwords (e.g., "AI-powered magic", "frictionless ROI") that automatically trigger heightened skepticism.
  * `default_action`: Defaulting to inaction/status quo.

---

### Component 5: The Cold-Isolated Secret Ballot Topology
* **Academic Source**: Sushil Bikhchandani, David Hirshleifer, & Ivo Welch (1992), *"A Theory of Fads, Fashion, Custom, and Cultural Change as Informational Cascades"* (*Journal of Political Economy*); Carolin Kaiser et al. (2025), *"Simulating Human Opinions with Large Language Models"*.
* **The Provenance**: Multi-agent interaction research proves that placing agents in a shared group chat triggers immediate **Information Cascades**: the first agent to output tokens anchors the conversation, and subsequent agents align with the emergent consensus due to attention recency.
* **Engineering Translation**: The skill strictly mandates that **Phase 2 Secret Ballot** must execute via parallel, isolated sub-agents with zero inter-agent communication. Group deliberation is only used downstream to observe debate dynamics after the uncorrupted baseline votes are locked.

---

### Component 6: Conjoint & Discrete Choice Elicitation
* **Academic Source**: James Brand, Ayelet Israeli, & Donald Ngwe (2024), *"Using GPT for Market Research"* (*Harvard Business School / ACM EC 2024*).
* **The Provenance**: Brand et al. proved that querying LLMs with Conjoint Analysis (discrete choice between competing feature/price bundles and the status quo) generates downward-sloping demand curves and Willingness-to-Pay (WTP) estimates that quantitatively match empirical human benchmarks.
* **Engineering Translation**: The skill forces choices between `ADOPT_NOW`, `WAIT_AND_SEE`, and `REJECT_FOR_STATUS_QUO`, coupled with hard numerical dollar caps.

---

### Component 7: Immutable Persona Vectors & Pre-Registration
* **Academic Source**: J. David Cummins (2025–2026), *"The Threat of Analytic Flexibility in Using Large Language Models to Simulate Human Data"* (*Computational and Text Analysis Methods*).
* **The Provenance**: Cummins warned of "researcher degrees of freedom": researchers tweaking persona prompts until the model likes their proposal.
* **Engineering Translation**: Persona vectors are serialized and validated in immutable YAML schemas prior to proposal ingestion. Changing the persona during evaluation is strictly forbidden.

---

## 3. Upgradability Playbook: How to Evolve This Skill

As new computational social science and agentic simulation papers are published, follow this protocol to upgrade the skill:

### Upgrade Area 1: Calibration Curves (Ground-Truth Tuning)
* **Trigger**: When you acquire historical CRM data, win/loss sales call transcripts, or churn post-mortems.
* **Action**: Benchmark the synthetic panel against historical proposals. If the synthetic panel fails to predict past customer objections, calibrate the `loss_aversion_factor` and `status_quo_inertia` parameters until the simulation aligns with historical ground truth.

### Upgrade Area 2: Agent Memory & Dynamic Opinion Evolution
* **Trigger**: Advances in long-term agent memory architectures (e.g., hierarchical graph memory, temporal belief revision).
* **Action**: Allow synthetic personas to maintain persistent, evolving memory across multiple testing rounds. When you update a pitch, the persona should remember their past objections and check whether your new revision genuinely resolved them.

### Upgrade Area 3: Quantitative Conjoint Estimators
* **Trigger**: Integration of statistical discrete choice estimators (Multinomial Logit, Hierarchical Bayes).
* **Action**: Upgrade Phase 4 (Synthesis) to automatically fit a Multinomial Logit model over a 50-run silicon sample, outputting automated price elasticity curves and cross-attribute part-worth utilities.
