# URL Shortener — Agent Guide

This file provides essential context for AI agents working on this repository.

## What this project does

A minimal URL shortener service. Users `POST /shorten` with a URL and receive a short ID. Visiting `/r/:id` redirects to the original URL. Storage is in-memory (no database).

## Tech stack

| Layer | Technology |
|---|---|
| Runtime | Node.js 20+, ESM modules |
| Language | TypeScript (strict mode) |
| Framework | Express 4 |
| ID generation | nanoid 7-char IDs |
| Testing | Vitest + Supertest |

## Key files

```
src/app.ts      — Express app factory (createApp)
src/server.ts   — HTTP server entry point
src/store.ts    — UrlStore class (in-memory Map)
tests/          — Vitest test files (*.test.ts)
```

## Coding conventions

- **Named exports only** — no default exports
- **No `any`** — strict TypeScript throughout
- **ESM extensions** — imports use `.js` suffix (e.g. `import { createApp } from "./app.js"`)
- **Short IDs** — always use `nanoid(7)`
- **Pure factory** — `createApp` accepts dependencies as arguments; tests inject fakes
- Async route handlers must catch and forward errors explicitly

## Testing

- Every new route or `UrlStore` method needs a test in `tests/`
- Use Supertest against `createApp()` — never start a real server in tests
- Each feature needs at least one happy-path **and** one error-path test
- Run `npm test` before opening a PR; all tests must be green

## Do not touch

- `package.json` dependency versions (add packages, don't bump existing)
- `tsconfig.json`
- `.github/workflows/`

## PR conventions

- Branch: `feature/issue-<num>-<short-slug>`
- Title: `<type>: <description> (#<num>)` — types: `feat`, `fix`, `chore`, `docs`, `refactor`
- Open PRs as **draft**
- Description must include: summary, `Closes #<num>`, `npm test` output, any spec deviations

## When in doubt

Post a clarifying comment on the issue rather than guessing. Do not invent requirements.
