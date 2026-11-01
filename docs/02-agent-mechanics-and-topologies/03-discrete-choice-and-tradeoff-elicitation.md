# Module 2.3: Discrete Choice & Trade-Off Elicitation

> Implementing rigorous behavioral elicitation protocols: Conjoint Analysis, Van Westendorp Price Sensitivity, and Maximum Difference Scaling.

---

## 1. Beyond Open Questions: Why Structured Elicitation is Mandatory

When humans make decisions in the real world, they do not answer open prompts like *"Rate this on a scale of 1 to 10"*. 

Real humans make decisions through **constrained optimization**:
* *"Do I buy this expensive enterprise tier, or do I hire a junior engineer?"*
* *"Do I accept slower performance in exchange for higher data security?"*
* *"Do I spend three weeks learning a new system, or stay with the clunky tool I already know?"*

To elicit authentic predictive signals from LLM agents, we apply established econometric elicitation techniques.

---

## 2. Elicitation Method 1: Discrete Choice Experiments (Conjoint Analysis)

Conjoint analysis presents agents with profiles consisting of varying levels across key attributes.

### Attribute Matrix Construction:
* **Attribute 1: Deployment & Hosting**
  * Level A: Multi-tenant Cloud
  * Level B: Dedicated VPC
  * Level C: Self-hosted / Air-gapped
* **Attribute 2: Onboarding & Support**
  * Level A: Self-serve documentation only
  * Level B: Dedicated Slack channel + SLA
* **Attribute 3: Pricing Tier**
  * Level A: $49 / user / month
  * Level B: $149 / user / month
  * Level C: $20,000 / year flat enterprise license
* **Attribute 4: Security & Compliance**
  * Level A: SOC2 Type II verified
  * Level B: Standard TLS / Self-certified

### The Choice Task Prompt:
The persona is shown two randomly constructed alternative bundles plus the status quo:
> *"Review Package Alpha and Package Beta below. You have an immediate project deadline. Choose exactly ONE option that you would formally sign off on today: [Package Alpha, Package Beta, Neither / Status Quo]. State your governing reason in one sentence."*

---

## 3. Elicitation Method 2: Van Westendorp Price Sensitivity Meter (PSM)

To find the true psychological pricing bounds of an audience, the agent is prompted with the four classic Van Westendorp questions:

1. **Too Cheap**: At what price would you consider the product to be of such low quality that you would not trust it? ($P_{\text{too\_cheap}}$)
2. **Bargain / Good Value**: At what price would you consider the product a great deal, providing excellent value for money? ($P_{\text{bargain}}$)
3. **Expensive**: At what price does the product begin to feel expensive, requiring serious budget justification, but you would still consider purchasing? ($P_{\text{expensive}}$)
4. **Too Expensive**: At what price is the product simply prohibitive, leading to an immediate, non-negotiable rejection? ($P_{\text{too\_expensive}}$)

### Computing the Optimal Price Point (OPP):
By aggregating the responses across a panel of $N$ persona runs, we calculate the intersection where $P_{\text{too\_cheap}} = P_{\text{too\_expensive}}$, establishing the mathematically calibrated price corridor for the target market.

---

## 4. Elicitation Method 3: MaxDiff (Maximum Difference Scaling)

When evaluating feature lists, marketing hooks, or value propositions, standard rating scales suffer from "scale usage bias" (some agents rate everything 8/10, others rate everything 4/10).

MaxDiff eliminates this by forcing the agent to pick **Best** and **Worst** from a random subset of 4 or 5 statements:
> *"From the following 4 claims made in this proposal, select the SINGLE MOST COMPELLING claim that justifies your investment, and the SINGLE LEAST COMPELLING claim that you view as buzzword filler or irrelevant."*

This yields a mathematically transitive ranking of value propositions with high discriminative power.
