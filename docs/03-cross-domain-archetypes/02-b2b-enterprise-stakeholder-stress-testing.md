# Module 3.2: B2B Enterprise Stakeholder Stress-Testing

> Simulating the multi-headed enterprise buying committee: CFO, CISO, Procurement, and Lead Implementer.

---

## 1. The Anatomy of Enterprise B2B Purchasing

Unlike consumer purchases made by a single individual, enterprise software and service sales require consensus across a **buying committee** where each participant holds a distinct veto power:

```
+-----------------------------------------------------------+
|              THE ENTERPRISE BUYING COMMITTEE              |
+-----------------------------+-----------------------------+
| 1. ECONOMIC BUYER (CFO)     | 2. TECHNICAL CHAMPION       |
| - Controls purse strings    | - Suffers from the pain     |
| - Focus: ROI, payback speed | - Focus: Velocity, features |
| - Veto: Unfavorable terms   | - Veto: Bad DX, tech debt   |
+-----------------------------+-----------------------------+
| 3. RISK / SECURITY (CISO)   | 4. PROCUREMENT / LEGAL      |
| - Protects the perimeter    | - Enforces corporate rules  |
| - Focus: Audits, compliance | - Focus: MSA terms, SLA cap |
| - Veto: Data privacy breach | - Veto: Vendor lock-in      |
+-----------------------------+-----------------------------+
```

A B2B pitch that delights the Technical Champion will fail if it triggers the CISO's security alarms or the CFO's payback threshold.

---

## 2. Persona Specifications in B2B Simulation

### 1. The Skeptical CFO (Economic Buyer)
* **Core Metric**: Net Present Value (NPV), Payback Period (< 6 months), Total Cost of Ownership (TCO).
* **Guiding Heuristic**: *"Why spend capital today when we can defer this until next fiscal year?"*
* **Fatal Flaw Focus**: Unclear pricing tiers, seat-based expansion penalties, lack of verifiable case studies demonstrating hard dollar savings.

### 2. The Overburdened Lead Engineer (Implementer)
* **Core Metric**: Developer velocity, maintainability, architectural simplicity, zero midnight pages.
* **Guiding Heuristic**: *"Will this create more maintenance tickets for my team than it saves?"*
* **Fatal Flaw Focus**: Proprietary vendor lock-in, poor CLI/API tooling, undocumented edge cases, complex onboarding requirements.

### 3. The Enterprise CISO (Security Gatekeeper)
* **Core Metric**: Compliance posture (SOC2, ISO, HIPAA), zero data leakage, audit log completeness.
* **Guiding Heuristic**: *"Every new third-party vendor is an attack vector waiting to compromise our customer data."*
* **Fatal Flaw Focus**: Training AI models on customer inputs, multi-tenant database co-mingling, lack of role-based access control (RBAC) and SAML/SSO.

### 4. The Procurement Lead (Contractual Gatekeeper)
* **Core Metric**: Favorable payment terms (Net-60/90), renewal cancellation flexibility, penalty-backed SLAs.
* **Guiding Heuristic**: *"If this vendor goes bankrupt tomorrow, how exposed are we?"*
* **Fatal Flaw Focus**: Auto-renewing lock-in contracts, refusal to sign enterprise MSAs, uncapped liability.

---

## 3. The B2B Committee Simulation Workflow

1. **Phase 1: Isolated RFP / Deck Review**: Feed the sales deck, technical whitepaper, or landing page to all four personas independently. Extract their initial ratings and dealbreaker objections.
2. **Phase 2: Internal Committee Meeting**: Orchestrate a focus group where the Technical Champion pitches the software to the CFO, CISO, and Procurement Lead. Observe how well the pitch arms the champion with the arguments needed to overcome the committee's resistance.
3. **Phase 3: Sales Call Pre-Mortem**: Generate a prescriptive briefing for the sales team highlighting the exact questions each stakeholder will ask during live enterprise calls.
