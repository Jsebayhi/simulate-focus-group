# Module 2.4: Multi-Agent Focus Groups & Bandwagoning

> Operational directives for orchestrating simulated group discussions, neutral moderation, and detecting consensus divergence.

---

## 1. The Purpose of Simulated Focus Groups

While Secret Ballot elicitation captures unvarnished private individual sentiment, real-world business and purchasing decisions are inherently **collaborative and contested**:
* An engineer might champion an open-source tool, but the CFO demands vendor liability insurance.
* A consumer might find a feature intriguing, but their peer points out a glaring usability flaw.
* An executive team must reach a compromise under budget constraints.

The Multi-Agent Focus Group is designed to simulate these interpersonal friction dynamics under controlled conditions.

---

## 2. The Neutral Moderator Protocol

The Moderator Agent is not a participant in the debate. Its role is strictly structural:

* **Impartial Facilitation**: The moderator must never express an opinion on the product or steer the personas toward agreement.
* **Tension Probing**: When Stage 1 reveals an ideological or functional conflict between personas, the moderator explicitly puts that tension on the table:
  > *"Sarah (Engineering) says she needs this tool immediately to avoid team burnout. David (Finance), you noted that the annual contract fee requires canceling our existing observability vendor. How do the two of you resolve this trade-off?"*
* **Grounding Enforcement**: If a persona resorts to hand-waving or generic corporate jargon, the moderator intervenes:
  > *"David, specifically what line-item budget would you reallocate, and what is your timeline for reviewing this?"*
* **Time-Boxing**: The focus group is capped at 3 to 5 rounds of targeted cross-talk to prevent conversational drift and KV-cache bloat.

---

## 3. Detecting and Quantifying Bandwagoning

Bandwagoning (social conformity) occurs when a persona changes its private assessment simply to align with the dominant group voice.

Target Audience Simulator tracks the **Conformity Shift Index ($\Delta C$)**:

Let:
* $S_{\text{private}}$ be the persona's quantitative resonance score during the Stage 1 Secret Ballot.
* $S_{\text{delib}}$ be the persona's stated rating at the conclusion of the Stage 2 Focus Group.
* $\bar{S}_{\text{group}}$ be the mean score of the other participants in the room.

The shift is calculated as:
$$\Delta C_i = \big(S_{\text{delib}, i} - S_{\text{private}, i}\big) \cdot \operatorname{sgn}\big(\bar{S}_{\text{group}} - S_{\text{private}, i}\big)$$

* If $\Delta C_i > 0$, the persona succumbed to peer pressure and moved toward the group mean.
* If $\Delta C_i = 0$, the persona maintained its independent conviction.
* If $\Delta C_i < 0$, the deliberation actually deepened the persona's skepticism (polarization effect).

---

## 4. The Devil's Advocate Injection Technique

In panels where personas begin converging prematurely on polite agreement, the orchestrator has the option to inject a calibrated **Devil's Advocate sub-agent**:
* **Role**: A hyper-skeptical industry veteran whose explicit mandate is to expose edge cases, unstated costs, regulatory landmines, and competitor alternatives.
* **Function**: Stress-tests whether the group's emerging enthusiasm can withstand rigorous adversarial cross-examination.
