# Project: URL Shortener

## Overview
A tiny URL shortener service built with Express and TypeScript. Users POST a URL,
get back a short ID, and visiting `/r/:id` redirects them to the original URL.
Storage is in-memory (no database yet).

## Tech stack
- Runtime: Node.js 20+, ESM modules
- Language: TypeScript (strict mode)
- Framework: Express 4
- ID generation: nanoid
- Testing: Vitest + Supertest

## Directory structure
- src/app.ts       Express app factory (createApp function)
- src/server.ts    Entry point that starts the HTTP server
- src/store.ts     UrlStore class (in-memory Map-based storage)
- tests/           Vitest test files (*.test.ts)

## Coding conventions
- Named exports only — no default exports
- Strict TypeScript: no `any`, no implicit any
- ESM imports use `.js` extension (e.g. `import { createApp } from "./app.js"`)
- Use `nanoid(7)` for new short IDs
- Async route handlers must handle errors explicitly
- Keep `createApp` pure: accept dependencies as arguments so tests can inject them

## Testing requirements
- Every new route or store method requires a test in `tests/`
- Use Supertest against `createApp()` — do NOT start a real server in tests
- Run `npm test` before opening a PR; all tests must pass
- Add at least one happy-path and one error-path test per new feature

## Restricted areas (do NOT modify without explicit instruction)
- package.json dependency versions (only add, don't bump existing)
- tsconfig.json
- .github/workflows/

## PR conventions
- Branch name: `feature/issue-<num>-<short-slug>` (e.g. `feature/issue-3-custom-aliases`)
- PR title: `<type>: <description> (#<issue-num>)` where type is feat, fix, chore, docs, refactor
- PR must be opened as a DRAFT
- PR description must include:
  - Summary of changes
  - "Closes #<issue-num>"
  - Test results (paste output of `npm test`)
  - Any deviations from the issue spec, with reasoning

## When in doubt
If the issue is ambiguous or scope is too large, post a clarifying comment on the
issue instead of guessing. Do not invent requirements.
