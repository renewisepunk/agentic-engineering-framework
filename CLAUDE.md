# Agentic Engineering Framework

This project uses a Markdown-native workflow system for AI-assisted development.

## Before starting any task

1. Read `ai/CONTEXT.md` to understand the project.
2. Read `ai/STANDARDS.md` for engineering conventions.
3. Check `ai/knowledge/pitfalls.md` for known failure modes.

## Core workflow loop

Use the workflows in order. Each is a self-contained prompt you can run.

1. **Plan** — `ai/workflows/plan.md` — Turn a request into a concrete plan.
2. **Work** — `ai/workflows/work.md` — Implement the plan.
3. **Review** — `ai/workflows/review.md` — Assess the implementation.
4. **Compound** — `ai/workflows/compound.md` — Extract learnings back into the system.

## Run records

For significant changes, create a run folder:

```
ai/runs/YYYY-MM-DD_short-name/
  plan.md
  worklog.md
  review.md
  compound.md
```

Use the template in `ai/templates/plan.md` for the plan document.

## Rules

- Follow `ai/STANDARDS.md` for all code.
- Check relevant checklists in `ai/checklists/` before marking work as done.
- After every completed task, run the compound workflow to capture learnings.
- Do not skip the compound step. It is what makes the system improve over time.
