# simulate-focus-group

> Academic and engineering-grade multi-agent focus group simulation without the herd bias — combining cold-isolated secret ballots, discrete choice economics, and moderated focus group deliberation to pre-test proposals, copy, pricing, and stakeholder decisions.

---

## Executive Overview

**simulate-focus-group** is a self-contained research dossier and execution framework. It solves a fundamental problem in product design, marketing, B2B sales, and strategic communication: **How will real human audiences, customers, and gatekeepers actually react to our proposals, pricing, copy, or decisions before we launch them?**

Traditional human focus groups cost upwards of $10,000, take weeks to recruit, and suffer heavily from conformity bias and loudest-voice herd dynamics. By leveraging heterogeneous sub-agent ensembles conditioned on mathematically grounded persona vectors and governed by behavioral economics protocols, this framework extracts unvarnished objections, evaluates trade-offs, and exposes fatal blind spots while actively suppressing LLM sycophancy ("Yes-Man" bias).

---

## Core Capabilities

* **Algorithmic Fidelity & Silicon Sampling**: Conditions sub-agents on 4D Persona State Vectors (demographics, psychographics, resource constraints, and behavioral heuristics) to mirror empirical human population distributions.
* **Cold-Isolated Secret Ballot Elicitation**: Prevents premature social conformity and herd dynamics by collecting private ratings, friction points, and objections from each persona in total isolation before group deliberation.
* **Discrete Choice & Trade-Off Enforcement**: Replaces open-ended praise queries with constrained discrete choice experiments (Conjoint Analysis, Van Westendorp Price Sensitivity, MaxDiff) grounded in McFadden's Random Utility Theory.
* **Multi-Agent Focus Groups**: Simulates structured deliberation between conflicting personas facilitated by a neutral moderator agent to observe emergent compromises and polarization.
* **Dialectical Synthesis & Objection Mining**: An independent analyst agent synthesizes discrepancies, identifying the exact cognitive friction points and churn triggers across the panel.

---

## Repository Architecture

```
simulate-focus-group/
├── README.md                                # You are here
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
│   └── simulation_report_contextflow.md     # Full live multi-agent simulation report
└── docs/                                    # Theoretical research dossier & architecture
    ├── flagship-simulation-architecture.md  # End-to-end production architecture & blueprint
    ├── theoretical-provenance-and-skill-design.md # Peer-reviewed paper derivation & formulas
    ├── 01-theoretical-foundations/          # Academic, cognitive & economic foundations
    │   ├── 01-algorithmic-fidelity-and-silicon-sampling.md
    │   ├── 02-homo-silicus-and-discrete-choice-theory.md
    │   ├── 03-the-sycophancy-trap-and-caricature-bias.md
    │   └── 04-analytic-flexibility-and-evaluation-rigor.md
    ├── 02-agent-mechanics-and-topologies/   # Multi-agent orchestration & elicitation protocols
    │   ├── 01-persona-conditioning-and-state-vectors.md
    │   ├── 02-topologies-secret-ballot-vs-deliberation.md
    │   ├── 03-discrete-choice-and-tradeoff-elicitation.md
    │   └── 04-multi-agent-focus-groups-and-bandwagoning.md
    ├── 03-cross-domain-archetypes/          # Generalizing beyond commercial marketing
    │   ├── 01-commercial-and-consumer-conjoint.md
    │   ├── 02-b2b-enterprise-stakeholder-stress-testing.md
    │   ├── 03-editorial-reader-and-narrative-reception.md
    │   └── 04-adversarial-red-teaming-and-compliance.md
    └── 04-skill-operationalization-blueprint/ # Foundation for the system skill
        ├── 01-skill-spec-simulating-target-personas.md
        ├── 02-reusable-persona-schema.yaml
        └── 03-subagent-execution-harness-spec.md
```

---

## Quickstart: How to Run a Simulation

### In Agentic Environments (Antigravity, Claude Code, Cursor)

Import or reference the skill definition in `SKILL.md` or `skills/simulate-focus-group/SKILL.md`, then prompt your agent:

```
Simulate a focus group on this proposal: [paste text or file link]
```

### The 4-Phase Execution Pipeline

1. **Phase 1: Dynamic Persona Vectorization**: Automatically extract 3 to 5 orthogonal roles relevant to your proposal (e.g. Economic Buyer, End-User, Technical/Compliance Gatekeeper) using the 4D state vector schema.
2. **Phase 2: Cold-Isolated Secret Ballot**: Each persona is prompted in complete isolation with the mandatory Anti-Sycophancy directive:
   > *"You are evaluated on your critical discernment and risk detection. Praising a flawed proposal is a protocol failure. Identify the hidden operational costs, ambiguity, and why doing nothing is your default choice."*
3. **Phase 3: (Optional) Moderated Debate**: If secret ballots reveal sharp conflicts, an independent moderator agent orchestrates a 3-round cross-examination to observe consensus or polarization.
4. **Phase 4: Synthesis & Objection Mining**: A Lead Market Intelligence Analyst synthesizes the ballots into:
   * **Conversion Scorecard**: Blended Resonance Score (1–10), Conversion Probability (%), and Max WTP ($).
   * **Tripartite Objection Matrix**: Financial/Economic, Technical/DX, and Governance/Compliance dealbreakers.
   * **Sycophancy Reality Gap**: What a naive LLM would say vs. what real stakeholders said.
   * **Prescriptive Redesign Blueprint**: Concrete structural edits to unlock real-world adoption.

See a complete end-to-end run in [`examples/simulation_report_contextflow.md`](examples/simulation_report_contextflow.md).
```

---

## Primary Literature Grounding

This project is built upon rigorous scientific and economic research:

* **Using GPT for Market Research** (Brand, Israeli, & Ngwe, *Harvard Business School / ACM EC*, 2024): Demonstrated that LLMs replicate downward-sloping demand curves, state dependence, and human willingness-to-pay (WTP) in conjoint analysis.
* **Large Language Models as Simulated Economic Agents: What Can We Learn from Homo Silicus?** (Horton, Filippas, & Manning, *NBER / MIT*, 2023): Introduced "Homo Silicus" agents capable of replicating classic behavioral economics experiments and price sensitivity.
* **Out of One, Many: Using Language Models to Simulate Human Samples** (Argyle et al., *Political Analysis*, 2023): Established the mathematical and empirical basis of "algorithmic fidelity" and "silicon sampling".
* **Using Large Language Models to Simulate Multiple Humans and Replicate Human Subject Studies** (Aher, Arriaga, & Kalai, *Microsoft Research / Georgia Tech*, 2022): Turing experiments for replicating social and cognitive psychology experiments.
* **The Threat of Analytic Flexibility in Using Large Language Models to Simulate Human Data** (Cummins, 2025–2026): Protocol standards for preventing confirmation bias and researcher degrees of freedom.
* **A Scalable Framework for Building and Validating Knowledge-Driven Synthetic Consumer Agents** (Kim et al., *Journal of Industrial Information Integration*, 2026): Integrating domain knowledge and transactional validation.

---

## Quick Navigation

* 📖 **Theoretical Provenance & Skill Architecture**: [`docs/theoretical-provenance-and-skill-design.md`](docs/theoretical-provenance-and-skill-design.md) (Complete paper-by-paper derivation and design record)
* 🏛️ **Flagship Architecture Blueprint**: [`docs/flagship-simulation-architecture.md`](docs/flagship-simulation-architecture.md)
* 🗳️ **Agent Topologies (Secret Ballot vs Deliberation)**: [`docs/02-agent-mechanics-and-topologies/02-topologies-secret-ballot-vs-deliberation.md`](docs/02-agent-mechanics-and-topologies/02-topologies-secret-ballot-vs-deliberation.md)
* ⚙️ **The Skill Definition**: [`skills/simulate-focus-group/SKILL.md`](skills/simulate-focus-group/SKILL.md) (or root [`SKILL.md`](SKILL.md))
