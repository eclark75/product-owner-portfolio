# 04 · Daily Scrum Support and Risk Spotting

The course covered using AI to **predict risks and manage timelines**. As Scrum Master, I used it to spot patterns on the sprint board, not to run the Daily Scrum. The Daily Scrum belongs to the Developers.

## How it works
Before the Daily Scrum, the Scrum Master gives the AI a short, anonymized summary of the board. The summary uses only story IDs, statuses and days in progress. It includes no names and no customer data.

```
Role: You are a Scrum Master's assistant reviewing sprint health.

Context: Day 6 of 10. Sprint Goal: customers can submit a complete dispute in the app.
Board summary:
- CD-03 disclosures: In Progress 5 days, waiting on Compliance review
- CD-02 dispute reasons: Done
- CD-01 start dispute: In Progress 2 days, depends on CD-03
- CD-04 fraud routing: In Progress 3 days, waiting on Fraud team API details
- CD-05a photo evidence (stretch): Not started
Unplanned work this sprint: 1 production bug (fixed).

Task: Identify the top 3 risks to the Sprint Goal and suggest one question
the Scrum Master could ask the team about each.

Format: Numbered list.

Constraints: Team-level observations only. Do not assess individual performance.
```

## AI draft (example)
1. **CD-03 has been waiting on Compliance for 5 days, and CD-01 depends on it.** *Question:* "What do we need from Compliance to finish CD-03, and who can help us get it today?"
2. **CD-04 is waiting on another team.** *Question:* "Can we build against an agreed sample format while we wait for the API details?"
3. **The stretch item has not started.** *Question:* "Should we confirm with the PO that CD-05a moves to next sprint?"

## What the Scrum Master did
- Escalated the Compliance review through the Product Owner. The review came back the next day.
- Facilitated a quick working session with the Fraud team to agree on a sample format.
- Let the Developers decide in the Daily Scrum to drop the stretch item. The PO agreed.

**Result:** The Sprint Goal was met. The stretch item moved to Sprint 3.

## Guardrail
AI saw only story IDs and statuses. It never saw who was working on what, so it cannot become a tool for judging individuals.
