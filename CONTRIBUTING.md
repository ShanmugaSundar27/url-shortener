# Contributing to url-shortener

We welcome contributions! Here's how to help.

## How to report issues

If you've found a bug or have a feature request, please open a GitHub issue. Be as specific as possible—include steps to reproduce for bugs, what you expected to happen, and what actually happened. Check existing issues first to avoid duplicates.

## How to submit PRs

1. Fork the repo and create a feature branch: `feature/issue-<num>-<short-slug>`
2. Follow the coding conventions in CLAUDE.md: TypeScript strict mode, ESM imports with `.js` extensions, and named exports only
3. Write tests for new routes or store methods using Supertest, run `npm test` to verify all tests pass
4. Open your PR as a draft with a descriptive title (`<type>: <description> (#<issue-num>)`) and include a summary of changes plus test results
5. Address feedback from reviews and keep commits clean

## Code of conduct

We are committed to providing a welcoming and inclusive environment. Treat all contributors with respect, ask for clarification before assuming intent, and focus feedback on the code rather than the person. Harassment or discrimination of any kind will not be tolerated.
