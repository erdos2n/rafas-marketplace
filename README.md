# Rafa's Marketplace

Claude skills built by Rafael Carrasco, organized by category. Free to use.

## Install (Claude Code)

```
/plugin marketplace add erdos2n/rafas-marketplace
/plugin install adhd-communication@rafas-marketplace
```

Then restart Claude Code (or run `/reload-plugins`).

## Catalog

| Category (plugin) | Skill | Say / type | What it does |
|---|---|---|---|
| `adhd-communication` | `no-walls` | `/adhd-communication:no-walls` or "no walls" | Answer first, structure over prose, no walls of text |

## Always-on (optional)

Skills load when Claude decides they're relevant. To make no-walls apply to every session, add this line to `~/.claude/CLAUDE.md`:

```
Always follow the no-walls skill (adhd-communication plugin) for every response.
```

## Claude app (claude.ai)

There's no marketplace in the Claude app. Zip `plugins/adhd-communication/skills/no-walls/` and upload it under Settings → Capabilities → Skills.

## Adding a category

1. Create `plugins/<category>/.claude-plugin/plugin.json`
2. Add skills at `plugins/<category>/skills/<skill>/SKILL.md`
3. Add the plugin to `.claude-plugin/marketplace.json`
4. Bump the version in `plugin.json`
