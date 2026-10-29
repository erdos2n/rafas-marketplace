# Rafa's Marketplace

Claude Code plugins and skills by Rafael Carrasco, organized by category. Free to use under the [MIT License](./LICENSE).

## Install

From your terminal:

```bash
claude plugin marketplace add erdos2n/rafas-marketplace
claude plugin install communication-style@rafas-marketplace
```

Or inside a Claude Code session: `/plugin marketplace add erdos2n/rafas-marketplace`, then `/plugin install communication-style@rafas-marketplace`.

Run `/reload-plugins` or start a new session to load it.

## Update

```bash
claude plugin marketplace update rafas-marketplace
claude plugin update communication-style@rafas-marketplace
```

Then run `/reload-plugins` or start a new session. See [CHANGELOG.md](./CHANGELOG.md) for what changed.

> **Upgrading from `adhd-communication` (0.x)?** The plugin was renamed in 1.0.0. Run `claude plugin uninstall adhd-communication@rafas-marketplace`, then install `communication-style` as above.

## Catalog

| Plugin | Skill | What it does |
|---|---|---|
| `communication-style` | `adhd-communication` | Responses readable at a glance: answer first, structure over prose, no walls of text, questions you can't miss |

## Usage

| Command | Effect |
|---|---|
| `/adhd-communication` | On for the rest of the session |
| `/adhd-communication once` | Only the next reply |
| `/adhd-communication off` | Turn it off |
| `/adhd-communication <request>` | Turn it on and answer the request |

If another command already uses the short name, use the full name: `/communication-style:adhd-communication`.

In the Claude app, say it in plain words: "ADHD communication", "ADHD communication once", or "ADHD communication off".

Long sessions can push the skill out of context. If responses drift, invoke it again.

## Always-on (optional)

Skills load when Claude judges them relevant. To apply `adhd-communication` to every session, add this line to `~/.claude/CLAUDE.md`:

```
Always follow the adhd-communication skill (communication-style plugin) for every response.
```

## Claude app (claude.ai)

The Claude app doesn't install from marketplaces. Zip `plugins/communication-style/skills/adhd-communication/` and upload it under Settings → Capabilities → Skills.

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md). Every plugin change ships with a version bump and a changelog entry.

## License

[MIT](./LICENSE) © Rafael Carrasco
