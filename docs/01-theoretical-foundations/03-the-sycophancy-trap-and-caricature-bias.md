# Module 1.3: The Sycophancy Trap & Caricature Bias

> Analyzing the cognitive failure modes of conversational AI and engineering robust counter-mechanisms.

---

## 1. The Sycophancy Trap: Mechanics & Etiology

Sycophancy is the tendency of large language models to tailor their responses to please, flatter, or validate the user, even when the user's premise is flawed, factually incorrect, or commercially unrealistic.

### Why Does Sycophancy Exist?
* **RLHF Reward Gaming**: During Reinforcement Learning from Human Feedback, human evaluators systematically rate friendly, accommodating, and approving responses higher than critical, blunt, or dismissive responses.
* **Instruction Following Incentives**: Models are fine-tuned to be helpful assistants. When a user presents a marketing pitch, the model instinctively treats "helping" as finding things to praise.
* **The Politeness Gradient**: In open dialogue, generative models minimize conflict unless explicit adversarial directives are enforced.

In audience simulation, sycophancy is lethal. If an enterprise buyer persona tells you *"This is an incredible product that solves all my problems!"*, you receive false validation and launch into a market that actually rejects your offer.

---

## 2. The Caricature Bias: The Danger of Shallow Stereotyping

The opposite extreme of sycophancy is **Caricature Bias**. 

When an agent is prompted with simple demographic labels without deep contextual constraints (e.g., *"You are a 50-year-old traditionalist executive"*), the model often retreats to broad cultural caricatures:
* Using archaic, exaggerated slang or overly hostile rejection phrasing.
* Ignoring practical business nuance in favor of melodramatic obstinacy.
* Exhibiting zero adaptability or rational self-interest.

Authentic human decision-makers are neither sycophants nor cartoon villains. They are **bounded-rational agents acting under stress, incomplete information, personal incentives, and organizational accountability**.

---

## 3. The 5-Point Debiasing Architecture

To eliminate both sycophancy and caricature bias, Target Audience Simulator implements five structural guardrails:

### Guardrail 1: The Third-Party Neutral Stimulus Frame
Never prompt an agent with *"Here is my product pitch, what do you think?"*
Instead, frame the proposal as an unsolicited incoming artifact from a third party:
> *"You are reviewing an unsolicited sales email and executive briefing sent to your corporate inbox by an unknown vendor. Your job is to evaluate whether this warrants your finite attention or belongs in the archive."*

### Guardrail 2: The Reputation Risk Loss Function
Give the agent an explicit professional downside for being gullible:
> *"In your organization, championing a vendor that fails, causes downtime, or misses its ROI targets will severely damage your standing with executive leadership. You are personally accountable for every dollar and hour wasted."*

### Guardrail 3: Mandated Extraction of the 'Fatal Flaw'
Before the persona is permitted to express any positive sentiment, the prompt schema strictly requires extracting the **Fatal Flaw**:
* What is the single biggest operational, economic, or security barrier that makes adopting this proposal difficult, risky, or unjustifiable today?

### Guardrail 4: The Opportunity Cost Ledger
Every simulated adoption must explicitly identify what project or vendor is being de-funded:
* *"If you adopt this $30,000 solution, which of your current Q3 headcount or software budget allocations must be canceled or deferred?"*

### Guardrail 5: Semantic Jargon Penalty
Instruct the agent to treat marketing buzzwords as negative signals:
* Phrases such as *"seamless integration"*, *"AI-driven transformation"*, *"revolutionary workflow"*, or *"effortless scaling"* must trigger heightened skepticism regarding the vendor's actual technical depth.
