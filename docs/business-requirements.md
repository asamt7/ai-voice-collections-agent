# Business Requirements Document — AI Voice Collections Agent

> **Status:** Approved  
> **Version:** 1.0  
> **Prepared by:** Business Analyst (Portfolio Case Study — Anonymised)

---

## 1. Executive Summary

The client, a B2B services firm, required an AI-driven automation solution to replace their manual invoice collections process. This document captures the business requirements gathered through stakeholder discovery sessions, process walkthroughs, and client workshops.

---

## 2. Background & Current State

The client's collections team manually called customers to follow up on outstanding invoices. The process relied on:

- Individual agents working through a customer list in Excel
- Inconsistent script adherence
- Manual logging of call outcomes into spreadsheets
- No centralised view of collection status across the customer base

This approach was costly, inconsistent, and unscalable.

---

## 3. Business Objectives

| # | Objective |
|---|---|
| 1 | Automate outbound invoice reminder calls |
| 2 | Maintain professional, human-like customer interactions |
| 3 | Create a central repository for all invoice and interaction data |
| 4 | Provide admins with real-time status dashboards |
| 5 | Log every call as audio and transcription for audit purposes |
| 6 | Design for future extensibility (multilingual, CRM integration, SAAS) |

---

## 4. Stakeholder Map

| Stakeholder | Role | Interest |
|---|---|---|
| Operations Manager | Primary sponsor | Reduce manual effort, improve recovery rates |
| Finance Team | End user | Accurate invoice status, audit trail |
| IT / Development | Delivery | Technical feasibility, integration requirements |
| Customers | External | Professional, non-intrusive experience |

---

## 5. Functional Requirements

### 5.1 Central Invoice Repository

The system shall maintain a central data repository capturing:

- Invoice Date
- Services / Product Description
- Invoice Amount
- Payment Terms (e.g., Net 30, Net 60)
- Final Date for Payment
- Payments Received on Account
- Outstanding Balance
- Customer Details (name, contact, account ID)

### 5.2 AI Call Initiation

- The system shall automatically identify invoices that are due or overdue based on payment terms
- The system shall initiate outbound calls to customers at appropriate times
- The system shall support configurable calling schedules (time of day, frequency, escalation rules)

### 5.3 Conversational AI Agent

- The agent shall introduce itself as a virtual assistant (e.g., "Hello, I'm [Agent Name], [Company]'s virtual assistant")
- The agent shall handle natural language input in real-time
- The agent shall manage the following call scenarios:
  - General payment reminder
  - Customer not available / busy
  - Disputed invoice
  - Payment extension request
  - Abusive or uncooperative customer

### 5.4 Call Recording & Transcription

- Every call shall be recorded as an audio file
- Every call shall be transcribed and stored as searchable text
- Admins shall be able to review, download, or audit past interactions

### 5.5 Admin Dashboard

- Admins shall have a real-time view of all invoice statuses
- The dashboard shall display call outcomes and next-action recommendations
- The system shall surface recommended actions (e.g., "Verify Payment", "Escalate", "Follow-up Required")

### 5.6 Logging & Audit

- All call outcomes shall be automatically logged to the invoice repository
- The system shall schedule follow-up calls based on customer responses (e.g., "call me back Thursday")

---

## 6. Non-Functional Requirements

| Category | Requirement |
|---|---|
| Voice Quality | High-end human-like speech synthesis |
| Tone Adaptation | Agent adjusts tone based on detected customer sentiment |
| Availability | System operates during configurable business hours |
| Security | Enterprise-grade data security; call data encrypted at rest and in transit |
| Compliance | Configurable to meet regional compliance requirements |
| Scalability | Cloud-ready; designed to scale with call volume |

---

## 7. Future Scope (Phase 2+)

- Multilingual support and dialect customisation
- Integration with accounting platforms: Sage, Xero, QuickBooks
- API-based ERP integration for automatic invoice sync
- SAAS licensing model for third-party accounts software vendors

---

## 8. Acceptance Criteria

The PoC shall be considered successful when:

1. All 5 conversation scenarios execute correctly in test conditions
2. Call recordings and transcriptions are captured and retrievable
3. Invoice repository updates automatically following each call
4. Admin dashboard reflects real-time call outcomes
5. Stakeholder demo results in sign-off for pilot phase
