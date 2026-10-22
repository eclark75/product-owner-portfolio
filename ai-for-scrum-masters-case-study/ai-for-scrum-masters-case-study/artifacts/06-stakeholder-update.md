# 06 · Stakeholder Update (AI Draft → PO Final)

The course covered using AI to **improve team communication**. Product Owners write many updates. AI drafts them in business language, and the PO checks every fact before sending.

## The prompt
```
Role: You are a Product Owner writing to business stakeholders at a bank
(Card Operations, Compliance, Contact Center leadership).

Context:
- Sprint 2 Sprint Goal met: customers can submit a complete dispute in the app
  (correct reason and required disclosures) in the test environment.
- Fraud routing for "not recognized" claims is working with an agreed sample format.
- Photo evidence moved to Sprint 3.
- Risk: Final API from the Fraud team is needed by Sprint 3, Day 3.
- Ask: Compliance to name one approver for customer-facing text.

Task: Write a short update with three sections: Done, Next, Need from you.

Format: Under 150 words. Plain business language, no Scrum jargon.

Constraints: Use only the facts above. No dates or numbers that are not listed.
```

## Final update (after PO review)
**Subject: Mobile card disputes: Sprint 2 update**

**Done**
Customers can now start and submit a debit card dispute in the app, with the right dispute reason and the required disclosures. Claims marked "not recognized" are routed to the Fraud team. This is working in our test environment.

**Next**
In Sprint 3, customers will be able to attach a photo of a receipt, and we will start the case status tracker.

**Need from you**
- **Fraud team:** final API details by Sprint 3, Day 3, so routing can move beyond the sample format.
- **Compliance:** one named approver for customer-facing wording, so reviews don't stall.

**What the PO changed from the AI draft:** removed the words "fully compliant", which the AI had added and the PO could not support, and added "in our test environment" so stakeholders would not assume the feature was live.
