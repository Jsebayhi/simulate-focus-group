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

## Important Limitations & Ethical Scope

We believe in scientific humility regarding synthetic evaluations:

* **Not a Substitute for Human Empirical Research**: Synthetic personas cannot replicate the full richness, lived experiences, cultural contexts, or unanticipated behaviors of real human beings. They should be treated as a pre-flight falsification filter, never as the final verdict.
* **Distribution Flattening & Caricature Bias**: Language models can smooth over tail risks or collapse into stereotypical persona depictions if prompt constraints are insufficiently calibrated.
* **Temporal Drift & Calibration**: Persona utility functions require periodic grounding against real-world transactional data and qualitative interviews.

---

## Repository Structure

```
simulate-focus-group/
├── README.md                                # Project overview and theoretical grounding
├── SKILL.md                                 # Root system skill specification
├── skills/
│   └── simulate-focus-group/
│       └── SKILL.md                         # Portable skill definition
├── personas/                                # Production-ready persona definitions (YAML)
│   ├── b2b_cfo_skeptic.yaml
│   ├── b2b_lead_engineer.yaml
│   ├── b2b_ciso_compliance.yaml
│   └── consumer_budget_conscious.yaml
├── examples/
│   ├── sample_pitch.md                      # Reference pitch for simulation
│   └── simulation_report_contextflow.md     # Full reference multi-agent evaluation report
└── docs/                                    # Deep-dive theoretical dossier & architecture
    ├── flagship-simulation-architecture.md  # Detailed operational blueprint
    ├── theoretical-provenance-and-skill-design.md # In-depth paper-by-paper derivation
    ├── 01-theoretical-foundations/          # Cognitive & economic foundations
    │   ├── 01-algorithmic-fidelity-and-silicon-sampling.md
    │   ├── 02-homo-silicus-and-discrete-choice-theory.md
    │   ├── 03-the-sycophancy-trap-and-caricature-bias.md
    │   └── 04-analytic-flexibility-and-evaluation-rigor.md
    ├── 02-agent-mechanics-and-topologies/   # Orchestration & elicitation mechanics
    │   ├── 01-persona-conditioning-and-state-vectors.md
    │   ├── 02-topologies-secret-ballot-vs-deliberation.md
    │   ├── 03-discrete-choice-and-tradeoff-elicitation.md
    │   └── 04-multi-agent-focus-groups-and-bandwagoning.md
    ├── 03-cross-domain-archetypes/          # Domain adaptations
    │   ├── 01-commercial-and-consumer-conjoint.md
    │   ├── 02-b2b-enterprise-stakeholder-stress-testing.md
    │   ├── 03-editorial-reader-and-narrative-reception.md
    │   └── 04-adversarial-red-teaming-and-compliance.md
    └── 04-skill-operationalization-blueprint/ # Skill schemas and harness specifications
        ├── 01-skill-spec-simulating-target-personas.md
        ├── 02-reusable-persona-schema.yaml
        └── 03-subagent-execution-harness-spec.md
```

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
