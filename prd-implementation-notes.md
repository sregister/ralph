# Implementation Notes: Example Companion for `prd.json`

Use this optional file to capture development guidance that should accompany `prd.json` without expanding the PRD itself.

## Purpose

- Record implementation details that future Ralph iterations should follow.
- Keep product scope and user-facing requirements in `prd.json`.
- Keep technology, integration, validation, and verification guidance here.

## Technology Requirements

- Preferred language(s): [Specify if required]
- Required frameworks/libraries: [Specify if required]
- Runtime or version constraints: [Specify if required]
- Tooling requirements: [Specify if required]

## Architecture / Implementation Constraints

- Reuse these modules/services/components: [List paths or names]
- Follow these patterns/conventions: [Describe]
- Avoid these approaches: [Describe]
- Performance/security/data constraints: [Describe]

## Integration Notes

- External systems involved: [APIs, queues, webhooks, databases, vendors]
- Environment dependencies: [Local services, containers, staging systems]
- Test credentials, fixtures, or mocks: [Describe safe setup]
- Contract details or payload expectations: [Describe]

## Validation Plan

- Required checks beyond lint/typecheck/unit tests: [Describe]
- Integration tests to add or run: [Describe]
- System/end-to-end flows to validate: [Describe]
- Runtime assertions, observability checks, or logs to inspect: [Describe]

## Verification Steps

- Start required services: [Commands]
- Run validation commands: [Commands]
- Exercise these workflows manually or automatically: [Steps]
- Confirm these expected outcomes before marking a story complete: [Outcomes]

## Risks / Gotchas

- Known failure modes: [Describe]
- Edge cases to cover: [Describe]
- Setup pitfalls: [Describe]

## Open Questions

- [List unresolved implementation questions]
