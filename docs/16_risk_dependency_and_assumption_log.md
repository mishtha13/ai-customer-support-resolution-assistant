# Risk, Dependency & Assumption Log

## AI Customer Support & Resolution Assistant

**Company:** ServeFlow (fictional)  
**Purpose:** Identify and manage risks, dependencies, assumptions, and constraints associated with the MVP.

---

# 1. Risk Management Approach

Risks are evaluated using:

- **Likelihood:** Low / Medium / High
- **Impact:** Low / Medium / High
- **Severity:** Overall risk level
- **Mitigation:** Action to reduce likelihood or impact
- **Owner:** Responsible stakeholder
- **Status:** Open / Monitoring / Mitigated

The risk log should be reviewed throughout discovery, development, pilot, and rollout.

---

# 2. Risk Register

| ID | Risk | Likelihood | Impact | Severity | Mitigation | Owner | Status |
|---|---|---|---|---|---|---|---|
| R-01 | AI generates incorrect recommendations | Medium | High | High | Human review, confidence indicators, QA sampling | AI/Data | Open |
| R-02 | AI produces unsupported or hallucinated information | Medium | High | High | Ground responses in approved knowledge sources and monitor outputs | AI/Data | Open |
| R-03 | Low agent trust in AI recommendations | Medium | High | High | Explainability, feedback mechanisms, training, gradual rollout | Product | Open |
| R-04 | Agents over-rely on AI recommendations | Medium | High | High | Human approval for high-impact decisions | Product + Support Ops | Open |
| R-05 | Poor knowledge retrieval quality | Medium | High | High | Source ranking, retrieval evaluation, relevance feedback | AI/Data | Open |
| R-06 | Sensitive customer information exposed | Low | High | High | Role-based access, data minimization, security review | Security | Open |
| R-07 | AI recommendations increase resolution errors | Low | High | High | QA sampling, override capability, pilot monitoring | QA + Product | Open |
| R-08 | Low adoption among support agents | Medium | Medium | Medium | Training, change management, workflow integration | Support Ops | Open |
| R-09 | Existing support systems cannot integrate easily | Medium | High | High | Technical discovery and integration assessment before build | Engineering | Open |
| R-10 | AI response latency disrupts workflow | Medium | Medium | Medium | Performance testing and fallback to manual workflow | Engineering | Open |
| R-11 | Model performance varies by ticket category | Medium | Medium | Medium | Evaluate performance by category and prioritize weak areas | AI/Data | Open |
| R-12 | Pilot results are affected by ticket-mix differences | Medium | Medium | Medium | Compare similar ticket cohorts and control for complexity | Product Analytics | Open |

---

# 3. Highest-Priority Risks

## R-01 — Incorrect AI Recommendations

### Risk

The AI may recommend an incorrect classification, priority, or next action.

### Potential impact

Incorrect recommendations could result in:

- Delayed resolution
- Incorrect prioritization
- Incorrect escalation
- Customer dissatisfaction

### Mitigation

- Human review
- Confidence indicators
- QA sampling
- Agent override
- Performance monitoring

---

## R-02 — Unsupported AI Output

### Risk

The AI may generate information that is not supported by approved knowledge or ticket context.

### Mitigation

- Retrieval-augmented generation where appropriate
- Source references
- Approved knowledge base
- Output evaluation
- Human review for high-impact actions

---

## R-03 — Low Agent Trust

### Risk

Agents may not trust the recommendations and therefore avoid using the system.

### Mitigation

- Show confidence
- Allow edits
- Allow rejection
- Explain recommendations where practical
- Involve agents during pilot design
- Provide training

---

## R-04 — Over-Reliance on AI

### Risk

Agents may accept recommendations without sufficient review.

### Mitigation

- Human approval
- Explicit AI labeling
- Confirmation for high-risk decisions
- Training
- Monitor acceptance vs actual accuracy

---

# 4. Dependency Register

Dependencies are conditions that must be available for successful delivery.

| ID | Dependency | Type | Impact | Owner | Status |
|---|---|---|---|---|---|
| D-01 | Historical support-ticket data | Data | High | Data Team | Required |
| D-02 | Approved knowledge base | Data | High | Support Ops | Required |
| D-03 | Support platform integration | Technical | High | Engineering | To Assess |
| D-04 | AI/LLM infrastructure | Technical | High | AI/Data | Required |
| D-05 | Security & privacy review | Governance | High | Security | Required |
| D-06 | Agent participation in pilot | People | High | Support Ops | Required |
| D-07 | Product analytics instrumentation | Technical | Medium | Engineering | Required |
| D-08 | Stakeholder approval | Governance | Medium | Product | Required |
| D-09 | KPI definitions and baseline data | Analytics | High | Product Analytics | Required |
| D-10 | Training materials | Change | Medium | Product + Support Ops | Required |

---

# 5. Assumption Register

Assumptions represent conditions believed to be true but requiring validation.

| ID | Assumption | Why It Matters | Validation Method | Status |
|---|---|---|---|---|
| A-01 | Support agents spend significant time understanding complex tickets | Establishes value of summarization | Agent interviews/time study | To Validate |
| A-02 | Existing knowledge articles are sufficiently useful | Enables knowledge retrieval | Knowledge-base audit | To Validate |
| A-03 | Historical tickets are representative of common support problems | Supports model evaluation | Data analysis | To Validate |
| A-04 | Agents are willing to use AI assistance | Determines adoption potential | Pilot survey | To Validate |
| A-05 | AI recommendations can achieve acceptable accuracy | Determines production feasibility | Offline evaluation + pilot | To Validate |
| A-06 | Support workflows can accommodate AI assistance | Determines integration feasibility | Workflow review | To Validate |
| A-07 | Required customer data can legally and securely be processed | Determines data feasibility | Security/privacy review | To Validate |
| A-08 | AI assistance can reduce agent effort without reducing quality | Core product hypothesis | Controlled pilot | To Validate |
| A-09 | Product analytics can capture AI usage and feedback | Enables measurement | Analytics implementation | To Validate |
| A-10 | Business stakeholders agree on success criteria | Enables consistent evaluation | Stakeholder workshop | To Validate |

---

# 6. Constraints

The MVP is subject to several constraints.

### Data constraints

- Historical data may contain missing or inconsistent fields.
- Synthetic portfolio data cannot represent every production scenario.
- Some customer context may not be available to the AI.

### Technical constraints

- AI response latency may affect agent workflow.
- Integration with existing support systems may require additional engineering effort.
- Model performance may vary across categories.

### Organizational constraints

- Agent availability for pilot testing may be limited.
- Training and adoption require operational support.
- Stakeholders may have different priorities.

### Governance constraints

- Customer data must be handled according to applicable privacy and security requirements.
- High-impact AI recommendations require human oversight.

---

# 7. Risk Scoring Framework

A simple scoring model can be used:

```text
Risk Score = Likelihood × Impact
