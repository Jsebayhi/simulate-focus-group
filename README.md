# Target Audience Simulator

> An academic, engineering-grade multi-agent simulation framework for pre-testing human reception, consumer choice, client objections, and stakeholder decisions before real-world release.

---

## Executive Overview

Target Audience Simulator is a self-contained research dossier and execution framework. It solves a fundamental problem in product design, marketing, B2B sales, and strategic communication: **How will real human audiences actually react to our proposals, pricing, copy, or decisions before we launch them?**

By leveraging heterogeneous sub-agent ensembles conditioned on mathematically grounded persona vectors and governed by behavioral economics protocols, the simulator extracts unvarnished objections, evaluates trade-offs, and exposes blind spots while actively suppressing LLM sycophancy ("Yes-Man" bias).

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
target-audience-simulator/
├── README.md                                # You are here
├── docs/                                    # The comprehensive deep-dive research dossier
│   ├── FLAGSHIP_SIMULATION_ARCHITECTURE.md  # End-to-end production architecture & operational blueprint
│   ├── 01-theoretical-foundations/          # Academic, cognitive & economic foundations
│   │   ├── 01-algorithmic-fidelity-and-silicon-sampling.md
│   │   ├── 02-homo-silicus-and-discrete-choice-theory.md
│   │   ├── 03-the-sycophancy-trap-and-caricature-bias.md
│   │   └── 04-analytic-flexibility-and-evaluation-rigor.md
│   ├── 02-agent-mechanics-and-topologies/   # Multi-agent orchestration & elicitation protocols
│   │   ├── 01-persona-conditioning-and-state-vectors.md
│   │   ├── 02-topologies-secret-ballot-vs-deliberation.md
│   │   ├── 03-discrete-choice-and-tradeoff-elicitation.md
│   │   └── 04-multi-agent-focus-groups-and-bandwagoning.md
│   ├── 03-cross-domain-archetypes/          # Generalizing beyond commercial marketing
│   │   ├── 01-commercial-and-consumer-conjoint.md
│   │   ├── 02-b2b-enterprise-stakeholder-stress-testing.md
│   │   ├── 03-editorial-reader-and-narrative-reception.md
│   │   └── 04-adversarial-red-teaming-and-compliance.md
│   └── 04-skill-operationalization-blueprint/ # Foundation for the system skill
│       ├── 01-skill-spec-simulating-target-personas.md
│       ├── 02-reusable-persona-schema.yaml
│       └── 03-subagent-execution-harness-spec.md
├── personas/                                # Production-ready persona definitions (YAML)
│   ├── b2b_cfo_skeptic.yaml
│   ├── b2b_lead_engineer.yaml
│   ├── b2b_ciso_compliance.yaml
│   └── consumer_budget_conscious.yaml
└── examples/
    └── sample_pitch.md                      # Reference pitch for simulation
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

* 📖 **Theoretical Provenance & Skill Architecture**: [`docs/THEORETICAL_PROVENANCE_AND_SKILL_DESIGN.md`](file:///mnt/Linux_DATA/projects_perso/perso-2nd-brain/repos/target-audience-simulator/docs/THEORETICAL_PROVENANCE_AND_SKILL_DESIGN.md) (Complete paper-by-paper derivation and design record)
* 🏛️ **Flagship Architecture Blueprint**: [`docs/FLAGSHIP_SIMULATION_ARCHITECTURE.md`](file:///mnt/Linux_DATA/projects_perso/perso-2nd-brain/repos/target-audience-simulator/docs/FLAGSHIP_SIMULATION_ARCHITECTURE.md)
* 🗳️ **Agent Topologies (Secret Ballot vs Deliberation)**: [`docs/02-agent-mechanics-and-topologies/02-topologies-secret-ballot-vs-deliberation.md`](file:///mnt/Linux_DATA/projects_perso/perso-2nd-brain/repos/target-audience-simulator/docs/02-agent-mechanics-and-topologies/02-topologies-secret-ballot-vs-deliberation.md)
* ⚙️ **The Skill Definition**: [`skills/target-audience-simulator/SKILL.md`](file:///mnt/Linux_DATA/projects_perso/perso-2nd-brain/repos/target-audience-simulator/skills/target-audience-simulator/SKILL.md) (Symlinked to `.agents/skills/target-audience-simulator`)
