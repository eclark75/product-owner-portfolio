# 05 · AI-Assisted Sprint Retrospective (Sprint 2)

The course covered **AI-powered facilitation**. In a Retrospective, AI groups the notes and the team does the thinking.

## Raw notes (anonymized before AI use)
**Went well**
- Disclosure text was approved faster once we booked the review early
- Refinement was quicker because stories came with draft acceptance criteria
- Fraud team session unblocked CD-04 in one meeting
- Daily Scrum stayed under 15 minutes

**Didn't go well**
- Waited 5 days on Compliance before escalating
- AI-drafted acceptance criteria missed accessibility again
- The test environment was down for a day
- Not clear who approves customer-facing wording

**Ideas**
- Add Compliance review to the Definition of Ready for customer-facing text
- Add accessibility to the refinement prompt
- Ask the platform team for test environment status alerts

## The prompt
```
Role: You are a neutral facilitator synthesizing a Sprint Retrospective.
Context (anonymized notes): {notes above}
Task: Group the notes into 3-4 themes, name a likely root cause for each,
and suggest one small, measurable improvement experiment per theme.
Format: Table with columns Theme | Evidence | Root cause | Experiment | Measure.
Constraints: Do not attribute comments to individuals. Do not add themes
that are not supported by the notes.
```

## AI draft (example), reviewed by the team
| Theme | Evidence | Root cause | Experiment | Measure |
|---|---|---|---|---|
| Compliance dependency | 5-day wait; faster when booked early | Review requested late in the sprint | Request reviews during refinement, before planning | Days waiting for review |
| AI drafts miss accessibility | Missed twice | Prompt does not mention accessibility | Add an accessibility line to the refinement prompt | AI drafts that include accessibility AC |
| Environment instability | Test environment down 1 day | No early warning | Ask the platform team for status alerts | Blocked hours per sprint |
| Unclear approvals | Unsure who approves wording | No named approver | PO confirms an approver for each story | Stories with a named approver |

## What the team chose
The team voted for **one** experiment: *add an accessibility line to the refinement prompt*. It was the smallest change, and the team could make it without depending on anyone else.

The Compliance experiment was also adopted as a Definition of Ready update, because the PO could make that change directly.

## Updated refinement prompt (constraint added)
```
Constraints: ... Always include at least one accessibility acceptance criterion
(for example screen reader support or color contrast).
```
