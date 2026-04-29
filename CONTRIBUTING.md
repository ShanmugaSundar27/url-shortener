# Contributing to url-shortener

We welcome contributions! Here's how to help.

## Development setup

### Prerequisites
- Node.js 20 or later
- npm (comes with Node.js)

### Getting started
1. Clone the repository: `git clone https://github.com/ShanmugaSundar27/url-shortener.git`
2. Install dependencies: `npm install`
3. Run tests: `npm test` — all tests must pass before opening a PR
4. Start the development server: `npm run dev`

The server will run on `http://localhost:3000` by default. Make changes to files in `src/` and tests in `tests/`, following the TypeScript and ESM conventions outlined in CLAUDE.md.

## How to report issues

If you've found a bug or have a feature request, please open a GitHub issue. Be as specific as possible—include steps to reproduce for bugs, what you expected to happen, and what actually happened. Check existing issues first to avoid duplicates.

## How to submit PRs

1. Fork the repo and create a feature branch: `feature/issue-<num>-<short-slug>`
2. Follow the coding conventions in CLAUDE.md: TypeScript strict mode, ESM imports with `.js` extensions, and named exports only
3. Write tests for new routes or store methods using Supertest, run `npm test` to verify all tests pass
4. Open your PR as a draft with a descriptive title (`<type>: <description> (#<issue-num>)`) and include a summary of changes plus test results
5. Address feedback from reviews and keep commits clean

## Commit message conventions

We follow conventional commits. Use one of these prefixes: `feat:` (new feature), `fix:` (bug fix), `docs:` (documentation), `chore:` (maintenance), `refactor:` (code refactoring), `test:` (tests). Examples: `feat: add delete endpoint (#5)`, `fix: handle empty URL input (#3)`, `docs: update API examples (#2)`.

## Code of conduct

We are committed to providing a welcoming and inclusive environment. Treat all contributors with respect, ask for clarification before assuming intent, and focus feedback on the code rather than the person. Harassment or discrimination of any kind will not be tolerated.
