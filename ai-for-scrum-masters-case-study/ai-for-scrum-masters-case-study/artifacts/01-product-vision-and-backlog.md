# 01 · Product Vision, Product Goal and Backlog

*Fictional scenario: the "Card Services" Scrum team at Harbor Point Bank (a made-up retail bank).*

## Product vision
Customers can resolve a problem with a card transaction from their phone, in minutes, without calling the bank, and always know where their case stands.

## Product Goal (next 3 sprints)
**Launch self-service card disputes in the mobile app for debit card transactions, with real-time status updates.**

Why it matters:
- Dispute calls are among the most frequent reasons customers contact the call center.
- Customers want to see the status of their case without having to ask for it.
- A digital flow captures complete information the first time, which reduces back-and-forth with the operations team.

## Stakeholders
| Stakeholder | What they care about |
|---|---|
| Card Operations | Complete, accurate dispute cases; manageable volume |
| Compliance & Risk | Regulatory timelines, disclosures, audit trail |
| Contact Center | Fewer dispute calls; agents can see the same status customers see |
| Fraud | Separating fraud claims from merchant disputes |
| Mobile Product Manager | Roadmap, customer satisfaction, app ratings |
| Customers | Speed, clarity, trust |

## Product Backlog (ordered)

Priority uses **cost of delay ÷ size**. Cost of delay = business value + time criticality + risk reduction (each 1-13). The score starts the conversation with stakeholders; the Product Owner makes the final call.

| # | ID | Backlog item | Value | Time | Risk | Size (pts) | Score | Ready? |
|---|---|---|---|---|---|---|---|---|
| 1 | CD-03 | Show required disclosures before submission | 5 | 13 | 13 | 3 | 10.3 | ✅ |
| 2 | CD-02 | Choose a dispute reason (not recognized, wrong amount, item not received) | 8 | 8 | 8 | 3 | 8.0 | ✅ |
| 3 | CD-01 | Start a dispute from a transaction in the app | 13 | 8 | 5 | 5 | 5.2 | ✅ |
| 4 | CD-04 | Route "not recognized" claims to the Fraud team | 8 | 8 | 13 | 5 | 5.8 | ✅ |
| 5 | CD-07 | Agents see the same case status in their desktop tool | 8 | 5 | 5 | 5 | 3.6 | ✅ |
| 6 | CD-06 | Case status tracker with push notifications | 13 | 5 | 3 | 8 | 2.6 | ✅ |
| 7 | CD-05 | Upload receipts or photos as evidence | 8 | 5 | 3 | 8 | 2.0 | ⚠️ needs refinement ([see 02](02-ai-backlog-refinement.md)) |
| 8 | CD-08 | "Make the dispute experience better" (stakeholder request) | ? | ? | ? | ? | – | ❌ too vague |

**How the order was set:** mostly by score, with one exception. CD-01 (5.2) sits above CD-04 (5.8) because a customer can't start a dispute until reasons and disclosures exist, and CD-01 completes that first end-to-end flow. CD-08 goes back to the stakeholder for a conversation before it can be scored.

## Definition of Ready (team agreement)
A backlog item is ready for Sprint Planning when:
- It is written as a user story with a clear user and outcome.
- It has testable acceptance criteria.
- It is small enough to finish in one sprint (8 points or less).
- Dependencies and compliance needs are known.
- The team has discussed it at least once in refinement.

## Definition of Done (team agreement)
- Code reviewed, tested and merged.
- Acceptance criteria met and accepted by the Product Owner.
- Accessibility check passed.
- Compliance and Risk sign-off recorded for customer-facing text.
- No customer data used in test environments.
