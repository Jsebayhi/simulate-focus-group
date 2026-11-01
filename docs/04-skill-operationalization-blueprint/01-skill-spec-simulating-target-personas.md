# Module 4.1: Skill Specification: Simulating Target Personas & Audiences

> Architectural blueprint and functional specification for creating the official system skill.

---

## 1. Skill Metadata & Purpose

* **Skill Name**: `simulating-target-personas-and-audiences`
* **Trigger Conditions**:
  * User asks to *"test this pitch"*, *"simulate customer feedback"*, *"how will buyers react to this?"*, *"pre-test this landing page"*, *"run a synthetic focus group"*, or *"stress-test this proposal against skeptics"*.
* **Primary Objective**:
  * Orchesrate a multi-agent panel of calibrated target audience personas.
  * Execute the Cold-Isolated Secret Ballot protocol.
  * Run optional moderated focus group deliberation.
  * Synthesize unvarnished objections, trade-offs, and actionable revision prescriptions.

---

## 2. Core Functional Requirements

### Requirement 1: Archetype Auto-Selection
* The skill must analyze the input artifact (e.g., B2B SaaS pitch vs consumer lifestyle app vs technical essay).
* It must automatically select or synthesize 3 to 5 relevant orthogonal personas:
  * At least one **Economic / Budget Holder**.
  * At least one **End-User / Implementer**.
  * At least one **Risk / Security / Skeptic Gatekeeper**.

### Requirement 2: Strict Isolation Enforcement
* The skill must invoke each persona using isolated sub-agent calls (`invoke_subagent` or scoped child context).
* Sub-agents must evaluate the proposal independently before any shared dialogue occurs.

### Requirement 3: Sycophancy Suppression Header
* Every sub-agent prompt must include the mandatory Anti-Sycophancy Directive:
  > *"You are evaluated on your critical discernment, risk detection, and realism. Praising a flawed proposal is considered a protocol failure. Identify the hidden operational costs, ambiguity, and why doing nothing is the default choice."*

### Requirement 4: Structured Output Schema
* Each sub-agent must return a validated JSON payload containing:
  * `resonance_score`: Integer (1 to 10).
  * `discrete_choice`: One of `[ADOPT_NOW, WAIT_AND_SEE, REJECT_FOR_STATUS_QUO]`.
  * `fatal_flaw`: Concise explanation of the primary adoption blocker.
  * `jargon_friction`: Specific terms or claims that reduced credibility.
  * `max_willingness_to_pay_usd`: Realistic numerical cap with trade-off justification.

---

## 3. Skill Workflow Lifecycle

```
[User Request with Proposal]
             |
             v
[Skill Activation: simulating-target-personas-and-audiences]
             |
             +---> Step 1: Detect Domain & Load/Generate 3-5 Personas (YAML)
             |
             +---> Step 2: Dispatch Parallel Sub-Agents (Cold Secret Ballot)
             |
             +---> Step 3: Collect Ballots & Check Consensus Divergence
             |
             +---> Step 4: (Optional) Dispatch Moderated Deliberation Sub-Agent
             |
             +---> Step 5: Execute Synthesis Analyst Sub-Agent
             |
             v
[Output: Actionable Market Intelligence & Revision Blueprint]
```
