# Rafa's Marketplace

Claude Code plugins and skills by Rafael Carrasco, organized by category. Free to use under the [MIT License](./LICENSE).

## Install

From your terminal:

```bash
claude plugin marketplace add erdos2n/rafas-marketplace
claude plugin install adhd-communication@rafas-marketplace
```

Or inside a Claude Code session: `/plugin marketplace add erdos2n/rafas-marketplace`, then `/plugin install adhd-communication@rafas-marketplace`.

Run `/reload-plugins` or start a new session to load it.

## Update

```bash
claude plugin marketplace update rafas-marketplace
claude plugin update adhd-communication@rafas-marketplace
```

Then run `/reload-plugins` or start a new session. See [CHANGELOG.md](./CHANGELOG.md) for what changed.

## Catalog

| Plugin | Skill | Invoke | What it does |
|---|---|---|---|
| `adhd-communication` | `no-walls` | `/adhd-communication:no-walls` or "no walls" | Responses you'll actually read: answer first, structure over prose, questions you can't miss |

## Always-on (optional)

Skills load when Claude judges them relevant. To apply `no-walls` to every session, add this line to `~/.claude/CLAUDE.md`:

```
Always follow the no-walls skill (adhd-communication plugin) for every response.
```

## Claude app (claude.ai)

The Claude app doesn't install from marketplaces. Zip `plugins/adhd-communication/skills/no-walls/` and upload it under Settings → Capabilities → Skills.

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md). Every plugin change ships with a version bump and a changelog entry.

## License

[MIT](./LICENSE) © Rafael Carrasco
