# Session Handoff

Last updated: 2026-05-20

## Current State

- Product version in the repo is `0.1.9`.
- The GitHub Action Marketplace display name is `Aici PR Gate`.
- The npm package is `@mgicloud/aici`.
- The core positioning is: tiny no-phone-home PR contract gates for AI output.
- Dependabot is temporarily disabled because GitHub Actions quota is constrained.
- Pushes should use `[skip ci]` until the quota resets.

## Recent Work

- Provider config is hardened: official OpenAI and Anthropic providers reject `baseUrl`; only `openai-compatible` accepts/requires `baseUrl`.
- Reports recursively redact configured secrets, bearer/API-key-like strings, tool-call arguments, and raw provider payloads.
- The GitHub Action runs the bundled `action-dist/cli.js`; `install` and `build` default to `false`.
- Artifact upload is opt-in by default.
- Docker strict-mode fixture guidance exists for `--network none` runs.
- A repository threat model exists at `docs/security/threat-model.md`.
- A HyperFrames product proof video is checked in at `site/assets/aici-pr-gate-proof.mp4`.
- Public strategy/outreach notes were cleaned from the public repo.

## Verification Baseline

Run locally:

```bash
npm run verify
npm audit --audit-level=moderate
npm pack --dry-run
```

Avoid using GitHub Actions while quota is constrained.

## Remaining Work

- Wait for GitHub Actions quota to reset.
- Create one canonical demo repo or PR with a real `Aici PR Gate` blocked merge.
- Re-enable Dependabot after quota resets if automatic update PRs are wanted again.
- Consider a small release-artifact gate for npm package hygiene.
- Do outreach only after there is at least one real blocked-PR proof link.
