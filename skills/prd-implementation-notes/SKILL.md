---
name: prd-implementation-notes
description: "Create a companion implementation-notes document for a PRD. Use when capturing technology choices, architecture constraints, environment setup, validation plans, or verification instructions that should guide implementation. Triggers on: create implementation notes, write prd implementation notes, add development notes, document validation plan."
user-invocable: true
---

# PRD Implementation Notes

Create a companion implementation-notes document for a PRD. This file captures development guidance that should inform future implementation without bloating the PRD itself.

---

## The Job

1. Identify the target PRD file.
2. Derive the companion notes filename by keeping the PRD basename and appending `-implementation-notes.md`.
3. Gather the implementation guidance that future coding iterations should follow.
4. Write or update the notes file in markdown.

For Ralph's root workflow, the default companion file is `prd-implementation-notes.md` next to `prd.json`.

Examples:

- `prd.json` -> `prd-implementation-notes.md`
- `tasks/prd-user-auth.md` -> `tasks/prd-user-auth-implementation-notes.md`

**Important:** Do not implement product code as part of this skill. Only create or refine the implementation-notes document.

---

## When To Use This File

Use the implementation-notes file for guidance such as:

- Required language, framework, library, or runtime choices
- Architecture constraints or preferred patterns
- Integration details for external systems or services
- Environment setup requirements and local/dev prerequisites
- Validation strategy beyond standard lint/typecheck/unit tests
- Verification steps that require runtime behavior, integration flows, or system testing
- Risks, gotchas, and guardrails that implementers should know before coding

Keep product scope, user value, and acceptance criteria in the PRD. Keep implementation strategy and validation detail here.

---

## Question Strategy

If the user has not already provided enough detail, ask targeted questions to fill the most important gaps. Prioritize:

1. Technology or platform constraints
2. Required integrations and dependencies
3. Validation and verification expectations
4. Environment or data setup requirements
5. Explicit non-goals or forbidden approaches

Ask only the questions needed to make the notes actionable.

---

## Recommended Structure

Use this structure unless the repository already has a stronger convention:

```markdown
# Implementation Notes: [Feature or PRD Name]

## Purpose
- Short explanation of how this file complements the PRD

## Technology Requirements
- Required languages, frameworks, libraries, versions, or tooling

## Architecture / Implementation Constraints
- Patterns to follow
- Existing modules or services to reuse
- Approaches to avoid

## Integration Notes
- External systems involved
- API contracts, queues, webhooks, databases, or services that matter
- Credentials, fixtures, mocks, or test environments needed

## Validation Plan
- Required checks beyond default quality gates
- Integration tests, end-to-end tests, smoke tests, or runtime assertions
- What must be validated before marking a story complete

## Verification Steps
- Exact manual or automated steps to confirm behavior
- Commands to run
- Environments or services that must be running
- Expected outputs or signals of success

## Risks / Gotchas
- Common failure modes
- Edge cases
- Setup pitfalls

## Open Questions
- Remaining unknowns that need clarification
```

---

## Writing Guidelines

- Be specific and operational.
- Prefer concrete commands, file names, systems, and expected results.
- Separate hard requirements from suggestions.
- Document verification in enough detail that a fresh agent iteration can execute it.
- If the notes mention external systems, say whether to use real systems, local emulators, mocks, or staging.
- If a validation step is expensive or optional, label it clearly.

---

## Example Guidance

Good notes include details like:

- "Use PostgreSQL row-level security policies instead of app-side filtering."
- "Write integration tests against the local Stripe mock, not the production sandbox."
- "To verify the worker flow, run `docker compose up redis worker` before executing the smoke test."
- "For browser verification, log in as `demo@example.com` and confirm the webhook status badge changes from Pending to Delivered."

Avoid vague notes like:

- "Use the best technology"
- "Test thoroughly"
- "Make sure integrations work"

---

## Checklist

Before finishing:

- [ ] Companion filename matches the PRD basename plus `-implementation-notes.md`
- [ ] Technology and architecture constraints are documented
- [ ] Validation and verification steps are concrete
- [ ] External system requirements are clear
- [ ] Open questions are listed if anything remains unresolved
