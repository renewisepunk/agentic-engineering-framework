# Agentic Engineering Framework

A drop-in, Markdown-native workflow system for AI-assisted development. It gives your coding agent (Cursor, Claude Code, Copilot, Aider, or anything else) a structured way to plan, implement, review, and — critically — learn from every task.

## The idea

Most AI coding workflows are stateless. You prompt, you get code, you move on. Nothing compounds.

This framework adds a feedback loop. Every completed task produces reusable knowledge — standards, checklists, pitfalls, patterns — that gets fed back into future tasks. The system gets better the more you use it.

The core loop:

```
Plan → Work → Review → Compound → Repeat
```

**Compound** is the key step. It asks: what went wrong, what went right, and what should we codify so the next task is easier?

## What's in the box

```
CLAUDE.md                    # Agent entry point — what to read, how to work
ai/
  CONTEXT.md                 # Project context (fill in per-project)
  STANDARDS.md               # Engineering standards (customize for your stack)
  workflows/
    plan.md                  # Turn a request into an actionable plan
    work.md                  # Implement with tests and a decision log
    review.md                # Multi-pass review against checklists
    compound.md              # Extract learnings back into the system
  checklists/
    plan.md                  # Quality gate for plans
    review.md                # Quality gate for implementations
  knowledge/
    pitfalls.md              # Failure modes to avoid (grows with use)
    patterns.md              # Approaches worth reusing (grows with use)
    decisions/               # Architecture Decision Records
  templates/
    plan.md                  # Plan document template
  runs/                      # Per-task records
```

14 files. No framework dependencies, no tooling lock-in, no config files. Just Markdown.

## Quick start

1. Copy the `ai/` folder and `CLAUDE.md` into your project root.
2. Open `ai/CONTEXT.md` and fill in your project details.
3. Customize `ai/STANDARDS.md` for your stack and conventions.
4. Point your agent at `ai/workflows/plan.md` and start your first task.

## How it works

Each workflow file is a self-contained, executable prompt. It defines a purpose, inputs, step-by-step procedure, expected outputs, and stop conditions (when to halt and ask a human).

| Step | Workflow | Produces |
|------|----------|----------|
| Plan | `workflows/plan.md` | Scoped plan with acceptance criteria and pre-mortem |
| Work | `workflows/work.md` | Code, tests, and a worklog of decisions |
| Review | `workflows/review.md` | Findings classified as must-fix, should-fix, or consider |
| Compound | `workflows/compound.md` | Updates to standards, checklists, and knowledge base |

### What compounds

After each task, the compound step can update:

- **Standards** — new rules born from real bugs
- **Checklists** — new checks that would have caught issues earlier
- **Pitfalls** — failure modes with symptoms, root causes, and prevention
- **Patterns** — approaches that worked and are worth reusing
- **Decisions** — architectural choices with context and rationale

### Run records

For significant changes, create a run folder under `ai/runs/`:

```
ai/runs/2026-04-30_add-auth/
  plan.md
  worklog.md
  review.md
  compound.md
```

This gives you a durable trail of how the project evolved and why.

## Design principles

- **Agent-agnostic.** Works with any coding agent that can read Markdown.
- **Framework-agnostic.** The system holds conventions, not framework dependencies.
- **Start lean, grow from pain.** Only 14 files to start. Add checklists, templates, and workflows when you feel the need — not before.
- **Checklists over vibes.** Reviews run against objective criteria, not gut feeling.
- **Knowledge over repetition.** Every mistake becomes a pitfall. Every good approach becomes a pattern.

## Expanding the framework

The initial set is deliberately minimal. When you hit friction, add to it:

- Need a security-focused review? Add `ai/checklists/security.md`.
- Releasing to production? Add `ai/workflows/release.md`.
- Onboarding new team members? Add context to `ai/CONTEXT.md`.
- Made a significant architecture decision? Add an ADR to `ai/knowledge/decisions/`.

The compound step naturally drives this expansion. You don't need to plan the framework — just use it and let it grow.

## License

MIT
