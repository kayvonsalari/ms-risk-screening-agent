# MS Risk Screening Agent

**Multi-agent clinical decision support system that flags patients for neurologist review — without replacing clinical judgement**

Delayed MS diagnosis is a significant clinical problem. Patients often present with fragmented symptoms across multiple visits — optic neuritis, sensory disturbances, fatigue, gait changes — that individually appear routine but collectively suggest neurological review is warranted. This system scans EHR-like records to surface those patients before they fall through the cracks.

---

## Business Outcome

- Reduces missed or delayed MS referrals by systematically screening patient populations
- Provides clinicians with a prioritised review list, not a diagnosis — human judgement remains central
- Operates with adjustable autonomy: recommendation-only mode for high-risk actions, with explicit escalation thresholds
- Generates transparent flagging rationale so clinicians understand why a patient was surfaced

---

## How It Works

Five agents collaborate across the Observe → Plan → Act → Reflect loop, each handling a distinct aspect of the screening task.

### Agent Roles

| Agent | Responsibility |
|---|---|
| Retrieval Agent | Pulls candidate patients from EHR-like records |
| Phenotyping Agent | Scores MS risk from structured symptom and history data |
| Notes / Imaging Agent | Summarises unstructured clinical notes and MRI descriptors |
| Safety & Governance Agent | Applies PHI handling policy and escalation rules |
| Coordinator | Combines evidence, sets autonomy level, produces flagging action |

### Adjustable Autonomy Model

```
Low-risk, routine patterns ──► Automated flag, no clinician input needed
Moderate signals ──────────► Flag with summary, clinician reviews
High-risk / ambiguous ─────► Escalation to neurology team with full evidence package
```

---

## Responsible AI Design

- **Screening, not diagnosis** — the system flags for review; it never makes a clinical decision
- **Explicit uncertainty** — agents communicate confidence levels and data gaps
- **PHI protection** — governance agent enforces data handling policy throughout pipeline
- **Transparency** — every flag includes the specific signals that triggered it
- **Human oversight** — clinician approval required before any patient-facing action

---

## Technologies

| Component | Technology |
|---|---|
| Agent Framework | LangChain / LangGraph |
| Data Simulation | Synthetic EHR dataset |
| Governance Layer | Safety & Governance Agent with policy rules |
| LLM | OpenAI GPT-4o |

---

## Part of

[Agentic AI Architecture — Johns Hopkins University](https://github.com/kayvonsalari)
