# Module 1.4: Analytic Flexibility & Evaluation Rigor

> Establishing epistemic standards, pre-registration protocols, and preventing confirmation bias in synthetic audience research.

---

## 1. The Cummins Critique: Researcher Degrees of Freedom

In *"The Threat of Analytic Flexibility in Using Large Language Models to Simulate Human Data"* (Computational and Text Analysis Methods, 2025–2026), J. David Cummins issued a critical warning to the computational social science and market research communities:

**The Risk of Prompt-Tuned Confirmation Bias**:
Because language models are sensitive to prompt phrasing, temperature settings, and model versions, a researcher who wants a specific outcome (e.g., proving their startup idea is viable) can easily engage in "prompt fishing":
* Tweaking the persona backstory until the simulated panel likes the product.
* Cherry-picking responses from high-temperature runs.
* Selectively ignoring personas that raised insurmountable objections.

Without strict methodological constraints, synthetic audience simulations degenerate into automated confirmation-bias machines.

---

## 2. The 4 Epistemic Standards for Rigorous Simulation

Target Audience Simulator adopts four procedural rules to guarantee scientific and commercial validity:

### Standard 1: Immutable Persona Definition (Pre-Registration)
* Persona state vectors must be compiled, validated, and frozen into deterministic YAML schemas **before** the target pitch or proposal is ingested.
* No alterations to persona risk tolerance, budget, or pain points are permitted in response to evaluation outcomes.

### Standard 2: Deterministic Panel Composition
* A panel must represent a balanced spectrum of stakeholder interests, including:
  * **The Economic Buyer**: Controls budget; prioritizes ROI and cost reduction.
  * **The Technical Implementer / User**: Experiences workflow friction; prioritizes stability, usability, and time-to-value.
  * **The Governance / Risk Officer**: CISO, legal, or procurement; prioritizes downside protection, data privacy, and compliance.
* The evaluator is prohibited from running simulations exclusively with friendly or enthusiastic persona types.

### Standard 3: Multi-Seed Replicate Sampling
* Because single runs can be influenced by random sampling noise, every critical evaluation must execute $N \ge 5$ independent stochastic passes (temperature $T \in [0.7, 0.9]$).
* Metrics must report confidence distributions:
  * Mean resonance score with standard deviation.
  * Fraction of runs resulting in outright rejection.
  * Recurring friction patterns that appear in $\ge 60\%$ of independent runs.

### Standard 4: Ground-Truth Calibration Anchors
* Whenever empirical data exists (e.g., historical sales call transcripts, win/loss post-mortems, churn surveys, published market research), the synthetic panel must first be benchmarked against known historical responses.
* If a synthetic panel cannot accurately replicate known historical customer objections, its predictions on unreleased proposals must be treated as uncalibrated.
