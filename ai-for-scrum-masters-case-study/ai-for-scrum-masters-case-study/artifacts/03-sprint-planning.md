# 03 · AI-Assisted Sprint Planning (Sprint 2)

## Inputs
- **Team:** 4 Developers, 1 QA, Scrum Master, Product Owner. Two-week sprints.
- **Capacity:** One Developer out 3 days, so capacity is about 90% of normal.
- **Recent completed work:** Sprint 1 completed 21 points; the team's reference range before this product was 20-26 points.
- **Ready items at the top of the backlog:** CD-03 (3), CD-02 (3), CD-01 (5), CD-04 (5), CD-07 (5), CD-05a (5).

## The prompt
```
Role: You are a Scrum Master facilitating Sprint Planning for a mobile banking team.

Context: Product Goal: launch self-service debit card disputes in the mobile app.
Recent completed work: 20-26 points per sprint. Capacity this sprint: about 90%.
Ready items: CD-03 disclosures (3), CD-02 dispute reasons (3), CD-01 start dispute (5),
CD-04 fraud routing (5), CD-07 agent view (5), CD-05a photo evidence (5).
CD-01 depends on CD-02 and CD-03.

Task: Draft two Sprint Goal options, suggest which items fit the capacity,
and list risks and dependencies the team should discuss.

Format: Two one-sentence goals, a bulleted forecast, then risks.

Constraints: The Developers decide the forecast. Do not invent dependencies.
```

## AI draft (example)
**Sprint Goal options**
- A: *A customer can start and submit a dispute in the app with the correct reason and disclosures.*
- B: *A customer can submit a dispute and contact center agents can see it.*

**Suggested forecast for Option A:** CD-03, CD-02, CD-01, CD-04 = 16 points, leaving room for unplanned work at reduced capacity.

**Risks to discuss**
- CD-03 needs Compliance sign-off on disclosure text; if it is late, CD-01 cannot be completed.
- CD-04 depends on how the Fraud team receives cases.

## What the team decided
- **Sprint Goal:** Option A, reworded by the team: *"Customers can submit a complete dispute in the app, with the right reason and required disclosures."*
- **Forecast:** CD-03, CD-02, CD-01, CD-04, plus CD-05a as a stretch item (21 points).
- **Risk actions:**
  - The PO books a Compliance review for disclosure text on Day 2.
  - The Scrum Master sets up a 15-minute check-in with the Fraud team on Day 1.

> The AI suggested 16 points. The Developers chose 16 committed points plus a 5-point stretch item. **AI informs; the team decides.**
