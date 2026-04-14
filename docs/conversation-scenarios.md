# Conversation Scenarios — AI Voice Collections Agent

> These scripts were designed by the Business Analyst as part of the requirements and UAT phase.  
> The AI agent ("[Agent Name]") uses these flows to handle real customer interactions.  
> Placeholders like `[Customer Name]`, `[Amount]`, `[Date]` are dynamically populated at runtime.

---

## Scenario 1 — General Payment Reminder

**Trigger:** Invoice is due or overdue. Customer has not yet been contacted this cycle.  
**Tone:** Soft, professional, non-confrontational.

| Turn | Speaker | Dialogue |
|------|---------|----------|
| 1 | **Agent** | Hello! This is [Agent Name], [Company]'s virtual assistant. Am I speaking to [Customer Name]? |
| 2 | **Customer** | Yes, speaking. |
| 3 | **Agent** | Great! I'm just here to remind you about an outstanding invoice for [Amount]. Would you like me to go over the details now? |
| 4 | **Customer** | Sure, go ahead. |
| 5 | **Agent** | Thank you! The invoice was issued on [Date], and the amount due is [Amount]. The final payment date is [Final Payment Date]. Will you be able to settle this by then? |
| 6 | **Customer** | Yes, I'll handle it by the due date. |
| 7 | **Agent** | Wonderful! If you have any questions, feel free to reach out. Thank you for your time, and have a great day! |

**Outcome logged:** `Payment Confirmed by Customer`  
**Next action for admin:** Monitor for payment receipt by due date.

---

## Scenario 2 — Not a Good Time / Customer Busy

**Trigger:** Customer is unavailable or does not wish to speak at the current time.  
**Tone:** Understanding, accommodating.

| Turn | Speaker | Dialogue |
|------|---------|----------|
| 1 | **Agent** | Hello! This is [Agent Name], [Company]'s virtual assistant. Am I speaking to [Customer Name]? |
| 2 | **Customer** | Yes, but I'm busy at the moment. |
| 3 | **Agent** | I understand! I don't want to take up too much of your time. Would you prefer I call back later or send an email with the invoice details? |
| 4 | **Customer** | Please send an email. |
| 5 | **Agent** | Of course! I'll send you the details right away. Thank you for your time, and have a great day! |

**Outcome logged:** `Email Requested — Follow-up Pending`  
**Next action for admin:** Confirm email sent; schedule follow-up call if no response within 48 hours.

---

## Scenario 3 — Disputed Invoice

**Trigger:** Customer disputes the validity of the invoice.  
**Tone:** Calm, empathetic, non-argumentative.

| Turn | Speaker | Dialogue |
|------|---------|----------|
| 1 | **Agent** | Hello! This is [Agent Name], [Company]'s virtual assistant, calling about invoice [Invoice Number] for [Amount]. |
| 2 | **Customer** | I don't think this invoice is correct. |
| 3 | **Agent** | I'm sorry to hear that. I'd like to make sure this gets resolved for you. Could you let me know what the concern is — is it the amount, the service description, or something else? |
| 4 | **Customer** | The amount doesn't match what we agreed on. |
| 5 | **Agent** | Thank you for letting me know. I'll flag this as a dispute and have someone from the team review it and get back to you within [X business days]. Is that okay? |
| 6 | **Customer** | Yes, that works. |
| 7 | **Agent** | Noted! Your dispute has been logged and our team will be in touch. Thank you for your patience. |

**Outcome logged:** `Invoice Disputed — Amount Discrepancy`  
**Next action for admin:** Verify Payment — Review invoice against agreed terms and contact customer.

---

## Scenario 4 — Payment Extension Needed

**Trigger:** Customer is unable to pay by the due date and requests an extension.  
**Tone:** Flexible but structured.

| Turn | Speaker | Dialogue |
|------|---------|----------|
| 1 | **Agent** | Hello! This is [Agent Name], [Company]'s virtual assistant, calling regarding invoice [Invoice Number] due on [Due Date]. |
| 2 | **Customer** | I'm aware, but I won't be able to pay by that date. I need more time. |
| 3 | **Agent** | I understand. Could you let me know when you'd be able to make the payment? |
| 4 | **Customer** | I can pay by [New Date]. |
| 5 | **Agent** | Thank you for letting us know. I'll log your requested extension to [New Date] and pass it on for review. You'll receive a confirmation shortly. |
| 6 | **Customer** | Thank you. |
| 7 | **Agent** | Of course! We appreciate your communication and look forward to resolving this. Have a great day! |

**Outcome logged:** `Extension Requested — New Proposed Date: [New Date]`  
**Next action for admin:** Follow-up Required — Approve or reject extension and notify customer.

---

## Scenario 5 — Abusive or Uncooperative Customer

**Trigger:** Customer becomes hostile, uses inappropriate language, or refuses to engage.  
**Tone:** Firm, calm, professional — does not escalate in kind.

| Turn | Speaker | Dialogue |
|------|---------|----------|
| 1 | **Agent** | Hello! This is [Agent Name], [Company]'s virtual assistant, calling about an outstanding invoice. |
| 2 | **Customer** | I don't want to talk to a bot. This is ridiculous. |
| 3 | **Agent** | I completely understand your frustration. I'm here to help resolve this as quickly as possible. The invoice for [Amount] is currently overdue. Would you prefer to speak to a human representative? |
| 4 | **Customer** | [Continues being hostile / uses inappropriate language] |
| 5 | **Agent** | I'm sorry you feel this way. For your records, this call has been logged. A member of our team will be in touch. I hope you have a better day. |

**Outcome logged:** `Customer Uncooperative — Escalate to Human Agent`  
**Next action for admin:** Escalate — Manual follow-up required by collections team.

---

## Key Design Principles

These scenarios were designed with the following BA-level decisions:

1. **Graceful degradation** — the agent always offers a human handoff option
2. **Audit completeness** — every call ends with a defined outcome code and next action
3. **Tone calibration** — soft scenarios use positive framing; escalation scenarios remain neutral and professional
4. **Minimal data collection** — agent does not request payment details over the phone; directs to secure channel
5. **Extensibility** — scenarios are structured as modular flows that can be extended (e.g., multilingual variants, dialect-specific tone adjustments)
