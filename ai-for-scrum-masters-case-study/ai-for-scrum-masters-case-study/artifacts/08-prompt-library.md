# 08 · Prompt Library for Scrum Masters and Product Owners

Reusable prompts built on the structure from **AI for Scrum Masters**: **Role → Context → Task → Format → Constraints.**
Replace anything in `{braces}`. Follow the [AI working agreement](07-ai-working-agreement.md): no customer or confidential data.

---

### 1. Refine a backlog item
```
Role: You are an experienced Product Owner coach for a {team type} Scrum team.
Context: Product Goal: {goal}. Backlog item: {item}. Requested by: {stakeholder group}.
Task: 1) Rewrite as a user story. 2) Propose 4-6 Given/When/Then acceptance criteria,
including one for accessibility. 3) If larger than one sprint, suggest 2-3 vertical slices.
4) List questions for stakeholders.
Format: Markdown with headings Story, Acceptance Criteria, Slices, Questions.
Constraints: Don't invent policies, regulations or numbers. Unknowns become questions. Draft for team review.
```

### 2. Split a large story
```
Role: You are an agile coach skilled in story splitting.
Context: Story: {story}. Estimated at {points} points; our sprints fit items up to {max} points.
Task: Suggest 3 ways to split it into vertical slices that each deliver customer value.
Name the splitting pattern used (workflow step, business rule, data type, etc.).
Format: Table: Slice | Value delivered | Pattern.
Constraints: Each slice must be testable on its own. Don't split by technical layer.
```

### 3. Draft Sprint Goal options
```
Role: You are a Scrum Master facilitating Sprint Planning.
Context: Product Goal: {goal}. Recent completed work: {range} points. Capacity: {capacity}.
Ready items: {list with points and dependencies}.
Task: Draft two Sprint Goals, suggest which items fit, and list risks.
Format: Two one-sentence goals, a bulleted forecast, then risks.
Constraints: The Developers decide the forecast. Don't invent dependencies.
```

### 4. Spot risks to the Sprint Goal
```
Role: You are a Scrum Master's assistant reviewing sprint health.
Context: Day {n} of {total}. Sprint Goal: {goal}. Board summary (IDs and statuses only): {summary}.
Task: Identify the top 3 risks to the Sprint Goal and one question to ask the team for each.
Format: Numbered list.
Constraints: Team-level only. Never assess individuals.
```

### 5. Synthesize a Retrospective
```
Role: You are a neutral facilitator.
Context (anonymized notes): {notes}
Task: Group into 3-4 themes, name a likely root cause, and suggest one measurable experiment per theme.
Format: Table: Theme | Evidence | Root cause | Experiment | Measure.
Constraints: No attribution to individuals. No themes without evidence.
```

### 6. Write a stakeholder update
```
Role: You are a Product Owner writing to {stakeholder groups}.
Context: Done: {outcomes}. Next: {items}. Risks: {risks}. Asks: {asks}.
Task: Write an update with sections Done, Next, Need from you.
Format: Under 150 words. Plain business language.
Constraints: Use only the facts given. No claims about compliance or dates unless listed.
```

### 7. Prepare for a difficult stakeholder conversation
```
Role: You are a coach helping a Product Owner prepare to say "not yet" to a stakeholder.
Context: Request: {request}. Why it isn't prioritized now: {reason}. Product Goal: {goal}.
Task: Suggest a short talking-points outline that acknowledges the need, explains the
trade-off and offers a next step.
Format: 4-6 bullet points.
Constraints: Respectful and specific. Don't promise dates.
```

### 8. Draft a Definition of Ready or Done
```
Role: You are an agile coach for a team in a regulated industry.
Context: Team type: {team}. Known needs: {e.g. compliance review, accessibility, security testing}.
Task: Draft a Definition of Ready and a Definition of Done for the team to discuss.
Format: Two short checklists.
Constraints: Keep each list to 7 items or fewer. Flag anything the team must confirm with Risk or Compliance.
```

## Prompting tips from the course, applied
- **Give a role.** It sets the expertise and tone.
- **Give only the context needed.** Less data means less risk.
- **Ask for a format.** Tables and headings are faster to review.
- **Set constraints.** "Don't invent" and "unknowns become questions" prevent made-up answers.
- **Iterate.** When a draft misses something, such as accessibility, fix the prompt, not just the output.
