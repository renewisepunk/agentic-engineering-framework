# AI Workflows

A Markdown-native framework for agentic development. Drop this `ai/` folder into any project to get a structured Plan > Work > Review > Compound loop.

## Quick start

1. Copy this `ai/` folder and the root `CLAUDE.md` into your repo.
2. Fill in `ai/CONTEXT.md` with your project details.
3. Customize `ai/STANDARDS.md` for your stack.
4. Run `ai/workflows/plan.md` on your first task.

## How it works

Each workflow file is a self-contained prompt. Open it, follow the steps (or feed it to your agent), and produce the specified outputs.

### Core loop

| Step | Workflow | What it produces |
|------|----------|-----------------|
| 1 | `workflows/plan.md` | A plan with acceptance criteria |
| 2 | `workflows/work.md` | Code + tests + worklog |
| 3 | `workflows/review.md` | Review findings + required fixes |
| 4 | `workflows/compound.md` | Updated standards, checklists, knowledge |

### The compound step matters

After completing a task, `workflows/compound.md` extracts what you learned and feeds it back into:
- `STANDARDS.md` (new rules)
- `checklists/` (new checks)
- `knowledge/pitfalls.md` (failure modes to avoid)
- `knowledge/patterns.md` (approaches that worked)

This is what makes the next task easier than the last one.

## Structure

```
ai/
  CONTEXT.md          # Project context (fill in per-project)
  STANDARDS.md        # Engineering standards
  workflows/          # The core loop
  checklists/         # Quality gates
  knowledge/          # Accumulated learnings
    decisions/        # Architecture Decision Records
  templates/          # Document templates
  runs/               # Per-task records (optional)
```

## Expanding the framework

Start lean. Add new checklists, templates, or workflow steps only when you feel the pain of not having them. The framework is designed to grow through the compound step, not through upfront planning.
