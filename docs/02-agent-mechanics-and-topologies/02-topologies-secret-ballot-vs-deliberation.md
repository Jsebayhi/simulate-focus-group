# Module 2.2: Topologies: Secret Ballot vs. Deliberation

> Comparing multi-agent interaction topologies and establishing why isolated individual elicitation must precede group discussion.

---

## 1. The Multi-Agent Interaction Dilemma

When designing a target audience or focus group simulation, system designers commonly pick one of two architectural extremes:
* **The Shared Group Chat**: All personas placed into a single conversational thread.
* **The Pure Independent Poll**: Each persona queried in complete isolation with no peer interaction.

Both approaches in isolation suffer from critical failure modes.

---

## 2. The Information Cascade Problem in Shared Chats

In behavioral sociology and complex systems, an **information cascade** occurs when individuals make decisions sequentially based on the observed actions of predecessors rather than their own private information signals (Bikhchandani, Hirshleifer, & Welch, 1992).

When multiple LLM agents are placed in a shared multi-turn context:
* **Token Recency Anchoring**: The agent speaking first sets the tone, vocabulary, and primary framing of the discussion.
* **Agreeableness Reinforcement**: Subsequent agents condition on the earlier responses in their context window. If the first persona is mildly positive, later personas attenuate their private objections to align with the emergent consensus.
* **Echo-Chamber Convergence**: By Turn 3 or 4, dissenting perspectives are completely suppressed. The group acts as a monolithic echo chamber.

---

## 3. The Limitation of Purely Isolated Polls

Conversely, if personas are only queried in total isolation:
* You miss **emergent trade-off negotiations** (e.g., how an engineer convinces a reluctant CFO to approve a critical technical tool).
* You cannot observe **rebuttal dynamics** (e.g., how a buyer reacts when an objection is directly answered with a counter-argument).
* Cross-functional coalition dynamics are entirely absent.

---

## 4. The Two-Stage Hybrid Topology: Secret Ballot First, Then Deliberate

To obtain the best of both worlds, Target Audience Simulator enforces a strict **Two-Stage Hybrid Topology**:

```
STAGE 1: COLD-ISOLATED SECRET BALLOT
[Target Artifact] ---> [Persona 1 Sub-Agent] ---> Private Ballot 1 (Locked)
[Target Artifact] ---> [Persona 2 Sub-Agent] ---> Private Ballot 2 (Locked)
[Target Artifact] ---> [Persona 3 Sub-Agent] ---> Private Ballot 3 (Locked)

STAGE 2: MODERATED DELIBERATION (FOCUS GROUP)
                   [Neutral Moderator]
                           |
          +----------------+---------------+
          |                |               |
 [Persona 1 Agent] <-> [Group Chat] <-> [Persona 2 Agent]
                           |
                   [Persona 3 Agent]

STAGE 3: DIALECTICAL SYNTHESIS
[Private Ballots 1,2,3] + [Deliberation Log] ---> [Analyst Agent] ---> Final Report
```

### Stage 1: The Secret Ballot (Pure Cold Isolation)
* Each persona sub-agent is invoked in its own pristine, isolated context window.
* It evaluates the proposal with zero awareness of what other personas think.
* It records its unvarnished rating, primary fatal flaw, and discrete choice.
* These ballots are permanently committed to disk as immutable ground-truth baselines.

### Stage 2: The Moderated Deliberation
* The Moderator Agent introduces the personas into a shared virtual room.
* The Moderator reveals key points of disagreement identified in Stage 1:
  > *"Marcus (CISO) expressed concern about data sovereignty in section 3, while Sarah (VP Product) indicated that the speed improvements justify the cloud deployment. Marcus, how do you respond to Sarah's priority?"*
* Personas debate, allowing the evaluator to observe how objections evolve under peer pressure or persuasive counter-arguments.

### Stage 3: Discrepancy & Drift Analysis
* The Analyst Agent compares the Stage 1 private votes against the Stage 2 public statements:
  * Which objections remained rock-solid despite debate? (These are true non-negotiable dealbreakers).
  * Which objections dissolved easily upon clarification? (These are simple messaging or documentation gaps).
