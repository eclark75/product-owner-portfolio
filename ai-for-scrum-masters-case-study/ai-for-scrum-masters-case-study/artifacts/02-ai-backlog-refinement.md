# 02 · AI-Assisted Backlog Refinement (Before → AI Draft → Team Final)

This is the clearest example of what I learned in **AI for Scrum Masters**: let AI draft the first version so the team spends refinement time on judgment instead of typing.

## The starting point
A stakeholder from Card Operations submitted this request:

> **CD-05:** "Customers should be able to add documents to disputes."

No user, no outcome, no acceptance criteria, no size.

## Step 1 · The prompt
Built with the structure taught in the course: **Role → Context → Task → Format → Constraints.**

```
Role: You are an experienced Product Owner coach for a mobile banking Scrum team.

Context: We are building self-service debit card disputes in our mobile app.
Backlog item: "Customers should be able to add documents to disputes."
Requested by Card Operations. Users are retail banking customers.

Task:
1. Rewrite this as a user story (As a / I want / so that).
2. Propose 4-6 acceptance criteria in Given/When/Then format.
3. If the work is larger than one sprint, suggest 2-3 vertical slices.
4. List questions the Product Owner should ask stakeholders.

Format: Markdown with headings Story, Acceptance Criteria, Slices, Questions.

Constraints: Do not invent policies, regulations or numbers. If something is
unknown, list it as a question. This is a draft for team review.
```

> **What I left out of the prompt on purpose:** customer names, account numbers, real case data and internal system names. Only fictional or generic information goes into an AI tool.

## Step 2 · The AI draft (example)

**Story**
As a customer disputing a card transaction, I want to attach a receipt or photo to my dispute so that the bank has the evidence it needs without contacting me again.

**Acceptance Criteria**
1. Given I am submitting a dispute, when I tap "Add evidence", then I can take a photo or choose a file from my phone.
2. Given I have attached a file, when I review my dispute, then I can see and remove the attachment before submitting.
3. Given a file is too large or an unsupported type, when I try to attach it, then I see a clear message explaining what is allowed.
4. Given I have submitted my dispute, when I view the case, then I can see that my evidence was received.
5. Given I attach a file, then it is encrypted in transit and at rest.

**Slices**
- Slice A: Attach photos from the camera (JPG/PNG).
- Slice B: Attach PDF files from the phone.
- Slice C: Add evidence to an existing case after submission.

**Questions**
- What file types and sizes does Card Operations need?
- How long must evidence be retained?
- Can customers add evidence after the case is submitted?

## Step 3 · What the team changed (human in the loop)

| AI draft | Team decision | Why |
|---|---|---|
| AC 5: "encrypted in transit and at rest" | Moved to the **Definition of Done** | It applies to every story, not just this one |
| Slice A and B as separate | **Kept**; Slice A planned for Sprint 2 | Photos are the most common evidence type |
| Slice C | **Moved to backlog** | Card Operations confirmed it is not needed for launch |
| Missing: accessibility | **Added AC:** screen reader announces attachment status | AI missed it; a Developer caught it |
| Question on retention | **Sent to Compliance** | The PO owns the answer, not the AI |

**Final:** CD-05 split into CD-05a (photo evidence, 5 pts, Ready) and CD-05b (PDF evidence, 3 pts, Ready). CD-05c (add evidence later) moved down the backlog.

## What this shows
- AI turned a one-line request into a discussable draft in seconds.
- The team still owned every decision. AI missed accessibility; people caught it.
- Open questions went to the people accountable for the answers.
