# Data Requirements — AI Customer Support & Resolution Assistant

## 1. Purpose

This document defines the data required to analyse ServeFlow's customer support process, establish baseline performance, identify operational pain points, and evaluate potential AI use cases.

The dataset will support both business analysis and product development activities.

---

## 2. Data Objectives

The data should allow the project to:

1. Understand the volume and distribution of support tickets.
2. Identify categories and issues generating the highest workload.
3. Analyse factors associated with long resolution times.
4. Identify drivers of SLA breaches and escalations.
5. Analyse repeat customer contacts.
6. Understand the relationship between support performance and CSAT.
7. Identify repetitive support scenarios suitable for AI assistance.
8. Evaluate the potential value of AI-assisted classification, summarization, knowledge retrieval, and response drafting.
9. Establish baseline KPIs against which the future-state solution can be evaluated.

---

## 3. Key Business Questions

The dataset should allow us to answer:

### Ticket Volume
- How many tickets are received over time?
- Which channels generate the most tickets?
- Which customer segments generate the highest ticket volume?

### Operational Performance
- Which categories have the longest resolution times?
- Which categories have the highest first-response times?
- Which issues have the highest SLA breach rates?

### Escalations
- Which categories are escalated most frequently?
- Does ticket priority influence escalation?
- Are certain product areas associated with higher escalation rates?

### Customer Experience
- What factors are associated with lower CSAT?
- Does longer resolution time correlate with lower CSAT?
- Are reopened or repeated tickets associated with lower satisfaction?

### Process Improvement
- Which ticket types appear repetitive?
- Which activities are suitable for AI assistance?
- Where is human review most important?

---

# 4. Data Dictionary

| Field | Data Type | Description | Purpose |
|---|---|---|---|
| `ticket_id` | String | Unique ticket identifier | Ticket tracking |
| `customer_id` | String | Unique customer identifier | Customer-level analysis |
| `created_at` | Datetime | Ticket creation timestamp | Trend and volume analysis |
| `channel` | Categorical | Support channel used | Channel analysis |
| `customer_tier` | Categorical | Customer segment/tier | Segment analysis |
| `subject` | Text | Short customer issue description | NLP / classification |
| `description` | Text | Detailed customer request | NLP / AI analysis |
| `category` | Categorical | Primary ticket category | Workload analysis |
| `sub_category` | Categorical | Detailed issue type | Root-cause analysis |
| `product_area` | Categorical | Product area associated with issue | Product insights |
| `priority` | Categorical | Ticket priority | SLA and workload analysis |
| `agent_id` | String | Assigned support agent | Agent-level analysis |
| `first_response_time_mins` | Numeric | Minutes until first response | Service performance |
| `resolution_time_hours` | Numeric | Hours until resolution | Resolution analysis |
| `status` | Categorical | Current/final ticket status | Workflow analysis |
| `escalated` | Boolean | Whether ticket was escalated | Escalation analysis |
| `reopened` | Boolean | Whether ticket was reopened | Resolution quality |
| `repeat_contact` | Boolean | Whether customer contacted support again for same issue | Recurrence analysis |
| `sla_breached` | Boolean | Whether applicable SLA was breached | SLA analysis |
| `csat_score` | Numeric | Customer satisfaction score | Customer experience |
| `resolution_type` | Categorical | How the issue was resolved | Resolution analysis |

---

# 5. Categorical Values

## Channel

Expected values:

- Email
- Live Chat
- Web Form
- In-App

---

## Customer Tier

Expected values:

- Standard
- Professional
- Enterprise

---

## Category

Initial categories:

- Billing
- Account
- Subscription
- Technical
- Product Usage
- Order
- Security
- Integration

---

## Priority

Expected values:

- Low
- Medium
- High
- Critical

---

## Status

Expected values:

- Resolved
- Escalated
- Closed

---

## Resolution Type

Expected values:

- Knowledge Base
- Agent Resolution
- Refund / Adjustment
- Configuration Change
- Technical Fix
- Escalated to Product
- Escalated to Engineering
- Customer Follow-up
- Other

---

# 6. Data Relationships

The dataset should support relationships between operational variables.

Examples:

```text
Category
    ↓
Resolution Time
    ↓
SLA Breach
    ↓
CSAT

    ↓
SLA Breach
    ↓
CSAT
