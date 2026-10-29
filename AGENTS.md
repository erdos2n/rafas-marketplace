# AGENTS.md

Instructions for AI agents working in this repository.

- Follow [CONTRIBUTING.md](./CONTRIBUTING.md) for layout, versioning, and the release checklist.
- Any change under `plugins/<plugin>/` must, in the same change:
  1. Bump `version` in `plugins/<plugin>/.claude-plugin/plugin.json` (semver)
  2. Add a `CHANGELOG.md` entry
- Do not add a `version` field to `.claude-plugin/marketplace.json`; `plugin.json` is the single source.
- This is a public repository. Never commit personal data, credentials, or private notes.
