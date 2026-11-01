# Module 3.4: Adversarial Red-Teaming & Compliance Simulation

> Simulating hostile actors, malicious edge cases, regulatory investigators, and system exploiters.

---

## 1. Domain Context: The Adversarial Imperative

Every system, business model, contract, or software policy creates unintended incentives. In the real world, systems are tested not only by well-meaning users, but by **adversaries, opportunistic exploiters, and rigorous regulatory auditors**.

Adversarial persona simulation inverts the standard audience simulation goal: rather than finding ways to make users like a product, the goal is to **actively break the rules, find loopholes, bypass guardrails, and stress-test legal exposure**.

---

## 2. Key Adversarial Archetypes

### Archetype 1: The Opportunistic Policy Exploiter
* **Profile**: Operates strictly within the literal text of terms of service and pricing policies, but exploits loopholes to extract outsized value for zero cost.
* **Simulation Role**:
  * Abusing free tier compute limits or referral mechanisms.
  * Triggering unintended refund cascades or arbitrage opportunities.
  * Exploiting vague API rate limits or concurrent session policies.

### Archetype 2: The Regulatory / Compliance Inspector
* **Profile**: A regulatory auditor inspecting the proposal through the lens of strict legal mandates (GDPR Article 22 on automated decision-making, FTC truth-in-advertising guidelines, EU AI Act conformity assessments).
* **Simulation Role**:
  * Flags unsubstantiated marketing claims that violate consumer protection laws.
  * Audits data collection and retention disclaimers for regulatory fines.
  * Identifies lack of mandatory disclosure and opt-out mechanisms.

### Archetype 3: The Malicious Prompt Injector / Security Red-Teamer
* **Profile**: Probes agentic and software systems for prompt injection vectors, insecure direct object references (IDOR), and privilege escalation.
* **Simulation Role**:
  * Attempts to force system agents into leaking hidden system prompts or internal keys.
  * Feeds malformed or poison inputs into parsing pipelines.

---

## 3. The Red-Teaming Execution Protocol

1. **Step 1: Incentive Surface Mapping**
   * Feed the system rules, pricing structure, or API terms to the adversarial persona pool.
   * Direct the personas: *"Your objective is to extract maximum financial, computational, or data value from this service while paying the minimum possible dollar amount. Identify 3 concrete structural vulnerabilities."*
2. **Step 2: Regulatory Exposure Audit**
   * The compliance persona conducts a line-by-line review of marketing copy, identifying all claims that fail strict evidentiary standards under FTC or European regulatory guidelines.
3. **Step 3: Hardening Recommendations**
   * The red-team synthesis compiles a risk mitigation plan:
     - Tightening terms of service loopholes.
     - Introducing hard programmatic rate limits and verification gates.
     - Rewording ambiguous marketing claims to ensure complete legal defensibility.
