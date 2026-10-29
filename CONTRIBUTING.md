# Contributing

Thanks for your interest. This marketplace is maintained by Rafael Carrasco; issues and pull requests are welcome.

## Repository layout

```
.claude-plugin/marketplace.json      Marketplace catalog
plugins/<plugin>/
  .claude-plugin/plugin.json         Plugin manifest (name, version, description)
  skills/<skill>/SKILL.md            One folder per skill
CHANGELOG.md                         Release history
```

## Versioning

Each plugin follows [Semantic Versioning](https://semver.org). The version lives in `plugins/<plugin>/.claude-plugin/plugin.json` only.

| Change | Bump | Example |
|---|---|---|
| Removing or renaming a skill or plugin | **Major** | `1.4.2` → `2.0.0` |
| Adding a skill, or new behavior in an existing skill | **Minor** | `1.4.2` → `1.5.0` |
| Wording, clarifications, fixes | **Patch** | `1.4.2` → `1.4.3` |

**Every change to a plugin's files must bump its version.** Claude Code decides whether an update is available from this version string; without a bump, users keep the old copy.

## Release checklist

1. Edit the skill(s) under `plugins/<plugin>/skills/`
2. Bump `version` in that plugin's `plugin.json`
3. Add an entry to `CHANGELOG.md`
4. If you added a skill or plugin, update the catalog table in `README.md`
5. For a new plugin, add it to `.claude-plugin/marketplace.json`

Keep all of the above in a single commit or pull request.

## Commit messages

`<plugin>: <what changed>`, for example `communication-style: highlight end-of-reply questions`.

## Skill guidelines

- One clear job per skill; the `description` frontmatter says when it should trigger
- Keep `SKILL.md` short enough to read in one sitting
- Test the skill in a Claude Code session before opening a PR
