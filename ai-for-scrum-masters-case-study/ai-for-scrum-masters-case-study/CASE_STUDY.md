# Case Study: Applying AI for Scrum Masters on a Digital Banking Scrum Team

**Focus:** How a Scrum Master and Product Owner can use generative AI responsibly to refine the backlog, plan sprints, spot risks, facilitate Retrospectives and communicate with stakeholders, in a regulated banking environment.

**Based on:** Scrum Alliance **AI for Scrum Masters** microcredential
**Supported by:** Certified Scrum Product Owner (CSPO) · ICAgile Business Agility Foundations (ICP-BAF)

> **About this case study:** This is an applied learning project. The bank ("Harbor Point Bank"), the team and the product are fictional. I created them to practice what I learned in the course end to end. The AI outputs shown are examples of the kind of drafts AI produces; the "team decisions" show how I would review and act on them as a Scrum Master and Product Owner. This project is not affiliated with any real bank.

---

## 1. The situation

The Card Services Scrum team at Harbor Point Bank was asked to launch **self-service debit card disputes in the mobile app**. Customers would be able to report a problem with a transaction and track their case without calling.

The team had four Developers, a QA engineer, a Scrum Master and a Product Owner, working in two-week sprints. They faced challenges common on banking teams:

- **Vague requests.** Stakeholders sent one-line asks like "Customers should be able to add documents to disputes."
- **Many stakeholders.** Card Operations, Compliance & Risk, Fraud, the Contact Center and the mobile Product Manager all had needs.
- **Dependencies outside the team.** Compliance review and Fraud team integrations could block work.
- **Strict data rules.** Customer information can never be pasted into an AI tool.

## 2. My goal

Apply what I learned in AI for Scrum Masters to **take repetitive drafting and summarizing off the Scrum Master and Product Owner**, so more time goes to the work that needs human judgment: stakeholder conversations, coaching the team and making value decisions.

**Product Goal:** Launch self-service card disputes in the mobile app for debit card transactions, with real-time status updates.

## 3. What I learned in the course, and how I applied it

| Course topic | How I applied it | Artifact |
|---|---|---|
| **Prompt engineering** | Built every prompt with the same five parts: Role, Context, Task, Format, Constraints | [08 Prompt library](artifacts/08-prompt-library.md) |
| **Streamlining workflows** | Used AI to turn one-line requests into draft user stories, acceptance criteria and slices before refinement | [02 Backlog refinement](artifacts/02-ai-backlog-refinement.md) |
| **AI-supported Sprint Planning** | Generated Sprint Goal options and a capacity-based forecast for the team to discuss | [03 Sprint Planning](artifacts/03-sprint-planning.md) |
| **Predicting risks and managing timelines** | Reviewed anonymized board summaries to spot dependency risks before they blocked the Sprint Goal | [04 Daily Scrum and risk](artifacts/04-daily-scrum-and-risk.md) |
| **AI-powered facilitation** | Grouped anonymized Retrospective notes into themes, root causes and measurable experiments | [05 Retrospective](artifacts/05-retrospective.md) |
| **Better team communication** | Drafted stakeholder updates in plain business language, then fact-checked them | [06 Stakeholder update](artifacts/06-stakeholder-update.md) |
| **Ethical AI use** | Wrote a team AI working agreement for a regulated environment before anyone used AI | [07 AI working agreement](artifacts/07-ai-working-agreement.md) |
| **Measuring impact** | Defined how the team would know whether AI was actually helping | [09 Measuring impact](artifacts/09-measuring-impact.md) |

## 4. How it played out

### Start with guardrails
Before any AI use, the team agreed to a working agreement. It covers:
- **Approved tools only.**
- **No customer data or confidential information** in prompts.
- **Every AI output is a draft** until a named person accepts it.
- **AI never makes priority, scope or release decisions**, and it is never used to evaluate individuals.

In a bank, this step comes first, not last.

### Build a backlog the team can deliver
As Product Owner, I wrote the product vision, Product Goal and an ordered backlog, along with a Definition of Ready and a Definition of Done. I set the order by **cost of delay ÷ size** and adjusted it for dependencies. Compliance sign-off and accessibility were built into the Definition of Done. → [01 Vision and backlog](artifacts/01-product-vision-and-backlog.md)

### Refinement: a one-liner becomes two sprint-ready stories
AI turned "Customers should be able to add documents to disputes" into a draft user story, five acceptance criteria, three slices and open questions. The team then:
- moved the encryption criterion into the Definition of Done
- **added an accessibility criterion the AI missed**
- sent the evidence-retention question to Compliance
- split the work into two ready stories and deferred the third slice

### Sprint Planning: AI informs, the team decides
AI drafted two Sprint Goal options and suggested 16 points at 90% capacity. The Developers chose 16 committed points plus a 5-point stretch item. AI also flagged the risk that Compliance review of the disclosure text could block the main story, so the PO booked that review for Day 2.

### During the sprint: catch risks early
On Day 6, AI review of an anonymized board summary surfaced three risks:
- The Compliance review had been waiting for 5 days.
- The Fraud team's API details were still pending.
- The stretch item had not started.

Here is how each was handled:
- I escalated the Compliance review through the PO.
- I facilitated a working session with the Fraud team.
- The Developers chose to drop the stretch item.

**The Sprint Goal was met.**

### Retrospective: improve the AI practice itself
AI grouped the notes into four themes. One theme was that **AI drafts kept missing accessibility**. The team fixed the prompt rather than just the output, adding a constraint that requires an accessibility acceptance criterion every time.

### Stakeholder update: check every claim
AI drafted the Sprint 2 update. As PO, I removed "fully compliant", which the AI added and I couldn't support. I also added "in our test environment" so no one would assume the feature was live.

## 5. Results I would track on a real team

This is a fictional team, so I am not reporting real performance numbers. These are the measures I set up to show whether AI is helping:

- **Refinement time per story**
- **% of stories Ready at Sprint Planning**
- **Sprint Goal met**
- **Days waiting on dependencies**
- **AI drafts accepted, edited or rejected**, which tells me whether the prompts are good
- **Team confidence in AI use**

Details are in [09 Measuring impact](artifacts/09-measuring-impact.md).

## 6. What I learned

1. **AI is a first-draft partner, not a decision-maker.** Its real value was giving the team something concrete to react to.
2. **Guardrails make adoption possible.** In a regulated environment, a clear working agreement is what lets a team use AI with confidence.
3. **AI makes mistakes people need to catch.** It missed accessibility and added an unsupported "fully compliant" claim. Human review is the control.
4. **Fix the prompt, not just the output.** When AI repeats a mistake, improving the prompt helps every future story.
5. **The Scrum Master role becomes more strategic.** With less time spent drafting and summarizing, more time goes to removing impediments and coaching.

## 7. How my other credentials support this

- **CSPO:** product vision, Product Goal, backlog ordering, user stories, acceptance criteria and stakeholder management.
- **ICP-BAF (Business Agility Foundations):** a customer-centric product vision, working across business functions (Operations, Compliance, Fraud, Contact Center), and continuous improvement driven by evidence.
