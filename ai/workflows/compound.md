# Workflow: Compound

## Purpose

Extract reusable knowledge from the completed task and feed it back into the system. This is the step that makes every future task easier. Do not skip it.

## Inputs

- The plan: `ai/runs/<run>/plan.md`
- The worklog: `ai/runs/<run>/worklog.md`
- The review: `ai/runs/<run>/review.md`

## Steps

1. **Reflect on the plan.** Answer:
   - What in the plan was wrong, missing, or underspecified?
   - What assumptions turned out to be incorrect?
   - What risks materialized? Were they anticipated?

2. **Reflect on implementation.** Answer:
   - What was harder than expected and why?
   - What decisions were made during implementation that should have been in the plan?
   - Were there recurring friction points?

3. **Reflect on review findings.** Answer:
   - What bugs were found? What was their root cause?
   - Were there patterns in the issues (e.g., always missing error handling for X)?
   - What would have caught these issues earlier?

4. **Update the system.** Based on the above, make concrete edits:

   **Pitfalls** (`ai/knowledge/pitfalls.md`):
   - Add any new failure mode discovered, with symptom, root cause, and prevention.

   **Patterns** (`ai/knowledge/patterns.md`):
   - Add any approach that worked well and is worth reusing.

   **Standards** (`ai/STANDARDS.md`):
   - Add or refine rules if a class of bug suggests a missing standard.

   **Checklists** (`ai/checklists/`):
   - Add new checklist items if the review caught something the checklist didn't.

   **Decisions** (`ai/knowledge/decisions/`):
   - If a significant architectural decision was made, record it as an ADR.

5. **Write the compound record.** Summarize what was captured in `ai/runs/<run>/compound.md`.

## Output

- Updated `ai/knowledge/pitfalls.md` (if applicable)
- Updated `ai/knowledge/patterns.md` (if applicable)
- Updated `ai/STANDARDS.md` (if applicable)
- Updated `ai/checklists/*.md` (if applicable)
- New ADR in `ai/knowledge/decisions/` (if applicable)
- `ai/runs/<run>/compound.md` summarizing changes

## Quality check

The compound step is done when you can answer "yes" to:
- Did I capture at least one concrete learning?
- Would a future agent benefit from what I wrote?
- Are the updates specific and actionable (not vague platitudes)?
