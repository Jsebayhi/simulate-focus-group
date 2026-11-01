# Module 1.2: Homo Silicus & Discrete Choice Theory

> Examining the microeconomic foundations of simulated economic agents and why discrete choice modeling outperforms open-ended elicitation.

---

## 1. Homo Silicus: The Artificial Economic Actor

In *"Large Language Models as Simulated Economic Agents: What Can We Learn from Homo Silicus?"* (NBER Working Paper 31122, MIT, 2023), John J. Horton, Apostolos Filippas, and Benjamin S. Manning coined the term **Homo Silicus** to describe LLM-powered artificial agents acting in simulated economic markets.

Horton's core thesis is that state-of-the-art language models possess an implicit "endowment of human-like behavioral tendencies" acquired through broad linguistic pretraining. When placed in economic scenarios, Homo Silicus exhibits:
* **Downward-Sloping Demand Curves**: As prices increase, simulated purchase quantity and adoption probability drop monotonically.
* **Loss Aversion**: Losses are weighted more heavily than equivalent gains (mirroring Kahneman & Tversky's Prospect Theory).
* **State Dependence**: Previous decisions and experiences condition future willingness-to-pay and brand loyalty.

---

## 2. The Brand, Israeli, & Ngwe Breakthrough (Harvard Business School, 2024)

In *"Using GPT for Market Research"* (ACM EC 2024), James Brand, Ayelet Israeli, and Donald Ngwe conducted the first large-scale empirical validation comparing simulated consumer choices directly to real human benchmark studies:

* **Conjoint Analysis Validation**: The authors tested thousands of simulated consumers on product feature bundles (e.g., consumer packaged goods, laptops).
* **Willingness-to-Pay (WTP) Concordance**: The estimated dollar-value premiums that GPT assigned to specific attributes (e.g., brand name, organic certification, battery life) matched human willingness-to-pay estimates from published empirical studies with remarkable precision.
* **Price Sensitivity Bounds**: Price elasticities derived from the synthetic population mirrored observed market elasticities, proving that LLMs can serve as low-cost pre-flight testbeds for market research.

---

## 3. The Failure of Open-Ended Elicitation

Why do naive prompts like *"Would you buy this software for $50/month?"* fail?

### Problem 1: Cheap Talk & Zero Constraint
In open-ended prompts, the model has no budget limit, no alternative spending priorities, and no consequence for saying "yes". Saying "yes" is the lowest-energy token path for an RLHF-aligned model.

### Problem 2: Hypothetical Bias
In behavioral economics, "hypothetical bias" is the phenomenon where humans state they will pay more in surveys than they will actually spend with real credit cards. In unconstrained LLMs, this bias is magnified tenfold.

---

## 4. Daniel McFadden's Random Utility Model (RUM)

To extract reliable economic decisions from LLM agents, we must enforce **Discrete Choice Analysis**, founded on Daniel McFadden's Nobel Prize-winning Random Utility Theory:

Let an agent choose among a finite set of mutually exclusive alternatives $\mathcal{J} = \{1, 2, \dots, J\}$.
The utility that persona $i$ derives from alternative $j$ is decomposed into a deterministic component $V_{ij}$ and a stochastic component $\epsilon_{ij}$:
$$U_{ij} = V_{ij} + \epsilon_{ij}$$

The deterministic utility $V_{ij}$ is a function of observable product attributes $\mathbf{x}_j$ (price, features, performance, risks) and persona characteristics $\mathbf{z}_i$ (budget, pain points, risk tolerance):
$$V_{ij} = \beta_i^\top \mathbf{x}_j - \alpha_i \cdot \text{Price}_j$$
where $\alpha_i$ represents the marginal utility of income (price sensitivity).

The probability that persona $i$ chooses alternative $k$ over all other options in $\mathcal{J}$ is given by the multinomial logit formulation:
$$P_{ik} = \frac{\exp(V_{ik})}{\sum_{j \in \mathcal{J}} \exp(V_{ij})}$$

---

## 5. Engineering Protocol: Constrained Choice Experiments

To apply Discrete Choice Theory in target audience simulation:

1. **Always Include the Status Quo**: The choice set must include Option 0: *"Do nothing / Keep existing process or tool ($0 incremental cost)"*.
2. **Bundle Trade-offs**: Force the agent to choose between competing trade-offs:
   - *Option A*: High capability, high price, complex integration.
   - *Option B*: Moderate capability, low price, instant setup.
   - *Option C*: In-house DIY workaround.
3. **Budget Depletion Invariant**: Remind the agent that selecting an option permanently deducts that sum from their finite department budget, preventing them from funding other ongoing initiatives.
