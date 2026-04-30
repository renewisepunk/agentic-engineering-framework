# Engineering Standards

These standards are enforced by the review workflow and checklists. Keep rules short, unambiguous, and enforceable.

<!-- Customize these for your stack. Delete what doesn't apply. Add what does. -->

## General

- Keep changes small and reviewable.
- Favor clarity over cleverness.
- Make dependencies explicit; avoid hidden coupling.
- One purpose per function/module.

## Error handling

- Validate inputs at system boundaries (user input, external APIs).
- Fail fast with actionable error messages that include context.
- Do not swallow errors. Propagate with context or handle explicitly.

## Logging and observability

- Log at boundaries and on state transitions.
- Never log secrets, credentials, or PII.
- Use structured logs where the stack supports it.

## Testing

- New behavior requires tests.
- Cover failure paths and edge cases, not just the happy path.
- Tests must be deterministic and isolated.
- Name tests to describe the expected behavior, not the implementation.

## Security

- Principle of least privilege for all access.
- Sanitize and validate all untrusted input.
- Secrets are never committed to the repository.
- Review authn/authz on every new endpoint or action.

## Performance

- Avoid N+1 query patterns.
- Bound expensive operations (pagination, timeouts, limits).
- Document performance assumptions in hot paths.

## Documentation

- Public API changes require doc updates.
- Include examples for non-trivial features.
- Keep docs next to the code they describe.
