# Module 4.3: Sub-Agent Execution Harness Specification

> Technical implementation details for invoking, managing, and parsing sub-agent simulation panels.

---

## 1. Sub-Agent Invocation Pattern

When executing audience simulation within Antigravity or any agent framework supporting `invoke_subagent`:

```python
# Conceptual orchestration logic in python/pseudo-code

def run_secret_ballot(proposal_text: str, persona_vector: dict) -> BallotResult:
    prompt = f"""
[IDENTITY & BEHAVIORAL DIRECTIVES]
You are simulating the following persona:
- Name: {persona_vector['metadata']['name']}
- Title: {persona_vector['demographics']['role']} ({persona_vector['demographics']['organization_type']})
- Risk Appetite: {persona_vector['psychographics']['risk_tolerance']} (0=Zero Risk, 1=Risk Seeker)
- Budget Limit: ${persona_vector['constraints']['discretionary_budget_usd']:,}
- Career Driver: {persona_vector['psychographics']['career_driver']}
- Career Nightmare: {persona_vector['psychographics']['career_nightmare']}

[ANTI-SYCOPHANCY INSTRUCTION]
You are an experienced, busy professional. You are skeptical of marketing promises.
Your career depends on avoiding wasteful spend and preventing operational disruptions.
You MUST identify risks, ambiguity, and unstated costs.

[PROPOSAL UNDER EVALUATION]
{proposal_text}

[EVALUATION TASK]
Provide a structured JSON output with the following keys:
1. "resonance_score": Integer from 1 to 10 (1=Instant Trash, 10=Must Buy Today).
2. "discrete_choice": "ADOPT_NOW" | "WAIT_AND_SEE" | "REJECT_FOR_STATUS_QUO"
3. "fatal_flaw": Concise statement of the single biggest blocker or risk.
4. "confusion_points": List of phrases or concepts that are vague or unsubstantiated.
5. "max_willingness_to_pay_usd": Maximum realistic dollar amount you would authorize today.
6. "internal_justification": Exactly what you would say to your CEO/board to defend this decision.
"""
    # Invoked via isolated subagent call
    response = invoke_subagent(
        TypeName="research",
        Role=f"Persona: {persona_vector['metadata']['archetype']}",
        Prompt=prompt
    )
    return parse_json(response)
```

---

## 2. Synthesis Analyst Sub-Agent Pattern

After all parallel sub-agents complete their Secret Ballot evaluations, an independent **Synthesis Analyst Agent** is invoked to process the collective intelligence:

```python
def run_synthesis_analysis(proposal_text: str, ballots: list[BallotResult]) -> SynthesisReport:
    prompt = f"""
You are the Lead Market Intelligence & Positioning Analyst.
Your role is to conduct an unvarnished audit of a target proposal based on empirical secret-ballot evaluations from a heterogeneous panel of stakeholders.

[TARGET PROPOSAL]
{proposal_text}

[RAW STAKEHOLDER BALLOTS]
{format_ballots(ballots)}

[SYNTHESIS MANDATE]
Analyze the consensus and divergence across the panel:
1. Friction Heatmap: Identify unanimous failure modes and credibility gaps.
2. Polarizing Trade-offs: Contrast where different stakeholders held conflicting priorities.
3. Willingness-to-Pay Elasticity: Compare price ceilings against stated value.
4. Prescriptive Action Plan: Provide 3 to 5 concrete structural edits to eliminate objections.
"""
    return invoke_subagent(
        TypeName="research",
        Role="Market Intelligence Analyst",
        Prompt=prompt
    )
```
