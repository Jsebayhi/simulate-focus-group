# Module 3.1: Commercial & Consumer Conjoint Simulation

> Applying the simulation architecture to consumer goods, digital subscriptions, e-commerce pricing, and onboarding flows.

---

## 1. Domain Context: Consumer Behavior & Price Elasticity

Consumer decisions differ significantly from B2B decisions:
* **Impulsive vs Deliberative**: Consumer choices are heavily influenced by cognitive load, emotional framing, immediate utility, and visual presentation.
* **Micro-Budgets & Friction Sensitivity**: A single friction point (e.g., forced account creation, surprise shipping fees, confusing checkout steps) causes instant abandonment.
* **Commodity Alternatives**: Consumers almost always have free or low-cost substitutes available.

---

## 2. Key Persona Archetypes in Consumer Simulation

### Archetype 1: The Budget-Conscious Optimizer
* **Profile**: Strict monthly discretionary budget; actively compares per-unit costs; seeks promotional codes; high churn propensity upon price increases.
* **Primary Trigger**: High initial friction or vague recurring subscription billing.
* **Simulation Role**: Tests price resistance floors and value proposition clarity.

### Archetype 2: The Convenience-First Maximizer
* **Profile**: Values time over marginal dollars; willing to pay premium for instant gratification, one-click ordering, or automated workflows.
* **Primary Trigger**: Sluggish loading times, complex multi-step forms, lack of mobile optimization.
* **Simulation Role**: Tests frictionless UX and premium tier willingness-to-pay.

### Archetype 3: The Skeptical Review Scourer
* **Profile**: Never buys based on vendor claims alone; searches immediately for third-party Reddit threads, YouTube reviews, or Trustpilot complaints.
* **Primary Trigger**: Over-promising marketing copy, absence of transparent negative reviews or return policy details.
* **Simulation Role**: Exposes credibility gaps and ungrounded marketing claims.

---

## 3. Conjoint Protocol for Consumer Products

To evaluate a consumer proposal (e.g., a new SaaS app or e-commerce bundle):

1. **Step 1: Baseline Preference Elicitation**
   * Feed product pitch or landing page copy to each consumer persona.
   * Query immediate reaction on a 5-point scale: [Definite No, Probably No, Maybe, Probably Yes, Definite Yes].
2. **Step 2: Attribute Trade-off Matrix**
   * Vary pricing tiers ($9/mo vs $19/mo vs $29/mo) against feature access (e.g., basic vs pro vs unlimited).
   * Measure the conversion cliff: the exact price threshold where purchase intent drops by more than 50%.
3. **Step 3: Cart Abandonment Autopsy**
   * Introduce simulated checkout hurdles (e.g., *"You must enter payment info before your 7-day trial begins"*).
   * Measure how many personas abandon the checkout funnel at that exact obstacle.
