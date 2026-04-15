# AI Voice Collections Agent - BA Case Study

> **Portfolio case study** | Sanitised for public sharing. Client and company names have been anonymised.

---

## Project Summary

| | |
|---|---|
| **Role** | Lead Business Analyst & AI Product Strategist |
| **Duration** | 3 months (Discovery → PoC sign-off) |
| **Domain** | FinTech / Accounts Receivable Automation |
| **Tech Stack** | AI Voice Agent, NLP, Cloud Telephony, Central Data Repository |
| **Methodology** | Agile (Scrum) |
| **Status** | PoC Approved - Advanced to Pilot |

---

## Problem Statement

A mid-sized B2B services firm was struggling with a high volume of overdue invoices. Their collections process was entirely manual - staff would call customers one by one, follow scripts inconsistently, and log outcomes into spreadsheets. Key pain points included:

- **High operational cost** of manual outreach across a large customer base
- **Inconsistent follow-up** - agents deviated from scripts, missed call-backs
- **No audit trail** - call outcomes were poorly logged, making reporting unreliable
- **Scalability ceiling** - the team couldn't scale collections volume without headcount growth

The client wanted an AI-powered solution that could autonomously contact customers, handle natural conversation, and log every interaction - reducing manual effort while maintaining a professional, human-like experience.

---

## Objectives

1. Automate outbound invoice reminder calls using a conversational AI agent
2. Handle key call scenarios: payment reminders, disputes, rescheduling, abusive customers
3. Build a central invoice repository with a real-time dashboard for admins
4. Record and transcribe every call for audit and continuous improvement
5. Design the system for future extensibility - multilingual support, CRM integration, SAAS licensing

---

## My Role & Deliverables

As the Lead Business Analyst, I owned the full requirements lifecycle from discovery through PoC approval:

| Deliverable | Description |
|---|---|
| **Business Requirements Document (BRD)** | Captured stakeholder needs, pain points, and success criteria |
| **Conversation Scenario Scripts** | Designed 5 structured call-flow scenarios (see `/docs`) |
| **Activity Diagram** | End-to-end AI agent process flow from invoice receipt to call logging |
| **Architecture Diagram** | System architecture including data source, telephony, AI engine, admin UI |
| **State Diagram** | Call state transitions (initiated → connected → outcome logged) |
| **Features Overview** | Functional feature breakdown for the development team |
| **UAT Script** | Test cases mapped to each conversation scenario |

---

## Solution Overview

The AI agent - named **"Kassandra"** — operates as follows:

```
Invoice Data Received → Repository Logged
         ↓
AI Checks Payment Terms & Due Date
         ↓
    Payment Due?
   ↙           ↘
  Yes            No → System waits, rechecks on due date
   ↓
AI Places Outbound Call (Human-like voice)
   ↓
Conversation Handled (one of 5 scenarios)
   ↓
Outcome Logged → Admin Dashboard Updated
   ↓
Next Action Recommended to Admin
```

### Key Capabilities

- **Intelligent Call Handling** - Schedules and places calls automatically based on payment terms
- **Human-Like Voice** - High-end speech synthesis; adjusts tone based on customer sentiment
- **Scenario-Based Logic** - Handles payment reminders, disputes, rescheduling, and difficult customers
- **Call Recording & Transcription** - Every interaction captured as audio + text
- **Admin Guidance** - Post-call system recommends next actions (e.g., "Verify Payment", "Escalate")
- **Continuous Learning** - QA feedback loops refine responses over time

---

## 💬 Conversation Scenarios Designed

| Scenario | Description |
|---|---|
| **1 — General Payment Reminder** | Soft-tone reminder for upcoming/overdue invoice |
| **2 — Not a Good Time** | Customer is busy; agent offers callback or email |
| **3 — Disputed Invoice** | Customer contests the charge; agent captures dispute and logs for review |
| **4 — Payment Extension Needed** | Customer requests more time; agent negotiates and logs agreed date |
| **5 — Abusive Customer** | Agent de-escalates, issues final reminder, terminates call professionally |

Full scripts available in [`/docs/conversation-scenarios.md`](docs/conversation-scenarios.md)

---

## Architecture

See [`/diagrams/`](diagrams/) for the full architecture diagram.

**High-level components:**

```
[ Data Source / Accounts System ]
           ↓
[ Central Invoice Repository + Admin Dashboard ]
           ↓
[ AI Orchestration Engine ]
    ↙              ↘
[ Telephony Layer ]   [ NLP / Speech Synthesis ]
           ↓
[ Customer (Outbound Call) ]
           ↓
[ Call Recording + Transcription Store ]
           ↓
[ Admin Notification + Next-Action Recommendation ]
```

**Integration Targets (PoC → Future):**
- Excel / CSV (PoC)
- Sage, Xero, QuickBooks (Phase 2)
- API-based ERP integration (Phase 3)

---

## Key Outcomes

| Metric | Result |
|---|---|
| Manual call effort reduction (projected) | ~70% |
| Call scenarios covered | 5 |
| Pilot approval | Secured after PoC demo |
| Admin dashboard views | Invoice log, transcription history, next-action queue |
| Future SAAS potential | Identified - white-label to Accounts software vendors |

---

## Repository Structure

```
├── README.md                          ← You are here
├── docs/
│   ├── business-requirements.md       ← BRD summary
│   ├── conversation-scenarios.md      ← All 5 call flow scripts
│   ├── features-overview.md           ← Functional feature breakdown
│   └── disclaimer.md                  ← Portfolio / anonymisation notice
├── diagrams/
│   ├── activity-diagram.png           ← End-to-end AI agent process flow
│   ├── architecture-diagram.png       ← System architecture
│   └── state-diagram.png              ← Call state transitions
```

---

## Tools & Skills Demonstrated

`Business Analysis` · `AI Product Strategy` · `Conversational AI Design` · `BRD / FRD` · `User Story Writing` · `Process Mapping` · `UML / Activity Diagrams` · `Stakeholder Workshops` · `UAT Planning` · `Agile / Scrum` · `Figma Wireframing` · `LLM Evaluation`

---

## Disclaimer

See [`/docs/disclaimer.md`](docs/disclaimer.md) for full details. All client and company names have been anonymised. Diagrams and documents are shared with permission for portfolio purposes only.
