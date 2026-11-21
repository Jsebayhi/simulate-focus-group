# simulate-focus-group

> An exploratory framework for multi-agent audience simulation and proposal stress-testing, building upon foundational research in computational social science, microeconomics, and AI alignment.

---

## Overview

Evaluating how real humans—whether customers, technical gatekeepers, or enterprise buyers—will respond to a proposal, pitch, pricing model, or essay is notoriously difficult before launch. Direct human testing (such as qualitative focus groups or surveys) is often conducted late in the development cycle, while naive LLM prompting (*"Act as a CFO and evaluate this"*) suffers from severe affirmative bias (sycophancy) and caricature stereotyping.

**simulate-focus-group** is an exploratory, open-source framework and research dossier designed to investigate a practical question:

> *Can we improve the qualitative realism of synthetic agent feedback by strictly operationalizing peer-reviewed methodologies from behavioral economics and computational social science?*

Rather than claiming to replace human subjects, this project proposes a structured pre-flight evaluation protocol. It combines **4D Persona State Vectors**, **Cold-Isolated Secret Ballots**, and **Discrete Choice Constraints** to surface unvarnished friction points, operational costs, and blind spots before presenting ideas to real-world stakeholders.

---

## Theoretical Foundations & Research Lineage

This framework does not introduce novel machine learning architectures; instead, it is an engineering synthesis humbly built upon empirical literature across multiple disciplines:

* **Algorithmic Fidelity & Silicon Sampling**:
  * *Argyle et al. (Political Analysis, Cambridge University Press, 2023)*: Demonstrated that conditioning language models on multi-dimensional demographic and ideological state vectors shifts token probability distributions into conditional sub-manifolds that mirror real human sub-populations.
  * *Aher, Arriaga, & Kalai (Microsoft Research / Georgia Tech, 2022)*: Investigated Turing experiments to replicate human subject behavioral studies with multi-agent ensembles.
* **Homo Silicus & Discrete Choice Theory**:
  * *McFadden (1974)*: Random Utility Theory ($U_{ij} = V_{ij} + \epsilon_{ij}$) establishing that decision-makers maximize utility under constrained trade-offs.
  * *Brand, Israeli, & Ngwe (Harvard Business School / ACM EC, 2024)*: Proved that LLMs can replicate downward-sloping demand curves, state dependence, and human willingness-to-pay (WTP) distributions in conjoint experiments.
  * *Horton, Filippas, & Manning (NBER / MIT, 2023)*: Introduced "Homo Silicus", demonstrating that simulated economic agents replicate core behavioral economics phenomena including price elasticity and status-quo inertia.
* **Information Cascades & Elicitation Topologies**:
  * *Bikhchandani, Hirshleifer, & Welch (Journal of Political Economy, 1992)* & *Kaiser et al. (2025)*: Showed that unconstrained multi-agent deliberations collapse into informational cascades and herd conformity when agents observe prior responses. This motivates our **Cold-Isolated Secret Ballot** stage prior to any cross-agent discussion.
* **Sycophancy Mitigation & Critical Evaluation**:
  * *Perez et al. (Anthropic / Alignment Research Center, 2022)* & *Sharma et al. (Anthropic, 2023)*: Documented that models optimized with RLHF tend toward conversational sycophancy, agreeing with user premises. We counteract this via explicit negative-utility prompting and mandatory fatal-flaw identification.
* **Methodological Rigor & Analytic Flexibility**:
  * *Cummins (Computational & Text Analysis Methods, 2025–2026)*: Highlighted the risk of "researcher degrees of freedom" in synthetic data generation, motivating our structured YAML schemas and standardized evaluation criteria.

---

## The 4-Phase Evaluation Protocol

```
[Target Proposal / Pitch / Artifact]
                  │
                  ▼
   Phase 1: Dynamic 4D Persona Vectorization
   (Demographics, Psychographics, Resource Constraints, Heuristics)
                  │
                  ▼
   Phase 2: Cold-Isolated Secret Ballot Elicitation
   (Independent sub-agents with strict Anti-Sycophancy Directives)
                  │
                  ▼
   Phase 3: (Optional) Moderated Multi-Agent Deliberation
   (Cross-examination on contentious trade-offs and divergence)
                  │
                  ▼
   Phase 4: Dialectical Synthesis & Objection Matrix
   (Independent analyst extracts core dealbreakers & redesign blueprint)
```

1. **Phase 1: 4D Persona Vectorization**: Derives 3 to 5 orthogonal roles balancing economic buyers, end-user implementers, and skeptical gatekeepers.
2. **Phase 2: Cold-Isolated Secret Ballot**: Each persona evaluates the artifact in total isolation, preventing herd bias and returning forced discrete choices (`ADOPT_NOW`, `WAIT_AND_SEE`, `REJECT_FOR_STATUS_QUO`), max willingness to pay, and fatal dealbreakers.
3. **Phase 3: Moderated Focus Group (Optional)**: If sharp ideological or operational disagreements emerge, an independent moderator orchestrates a 3-round cross-examination to observe whether objections harden or soften under debate.
4. **Phase 4: Synthesis & Objection Mining**: An independent analyst synthesizes individual ballots into a structured conversion scorecard, tripartite objection matrix (financial, technical, governance), and prescriptive redesign blueprint.

---

## Methodological Considerations

* **Distribution Flattening & Caricature Risk**: Language models can smooth over tail preferences or collapse into stereotypical archetypes if persona state vectors lack explicit economic constraints (budget ceilings, bandwidth limits, and loss aversion).
* **Empirical Grounding**: As established in Brand et al. (2024) and Horton et al. (2023), synthetic discrete choice models achieve highest predictive validity when calibrated against empirical choice baselines and benchmarked against real-world friction data.

---

## Quickstart

### Running with AI Agents (Antigravity, Claude Code, Cursor)

Include the skill definition from [`skills/simulate-focus-group/SKILL.md`](skills/simulate-focus-group/SKILL.md) or [`SKILL.md`](SKILL.md), then ask:

```
Simulate a focus group on this proposal: [paste text or reference file]
```

To see a complete end-to-end evaluation report generated by this protocol, inspect [`examples/simulation_report_contextflow.md`](examples/simulation_report_contextflow.md).

---

## Detailed Documentation & Research Dossier

* 📖 **Theoretical Provenance & Paper Derivation**: [`docs/theoretical-provenance-and-skill-design.md`](docs/theoretical-provenance-and-skill-design.md)
* 🏛️ **Flagship Architecture Blueprint**: [`docs/flagship-simulation-architecture.md`](docs/flagship-simulation-architecture.md)
* 🗳️ **Agent Topologies (Secret Ballot vs Deliberation)**: [`docs/02-agent-mechanics-and-topologies/02-topologies-secret-ballot-vs-deliberation.md`](docs/02-agent-mechanics-and-topologies/02-topologies-secret-ballot-vs-deliberation.md)
* ⚙️ **Skill Definition**: [`skills/simulate-focus-group/SKILL.md`](skills/simulate-focus-group/SKILL.md)
