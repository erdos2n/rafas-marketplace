# Changelog

All notable changes to this marketplace are documented here.
Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/); each plugin follows [Semantic Versioning](https://semver.org).

## communication-style

### [1.2.0] - 2026-11-18
#### Added
- `ask-less`: new skill that adds "act on reasonable defaults, ask only when necessary" rules to the project's CLAUDE.md (or `~/.claude/CLAUDE.md` with `global`). It keeps asking for destructive, irreversible, or out-of-repo actions, and moves optional extras to a "Could also:" line. Conflicting "ask first" lines are removed when the file is tracked in git, and listed otherwise. It warns when the file is shared. It changes instructions only, never permission settings, and deliberately sets no question timeout.

### [1.1.1] - 2026-11-18
#### Changed
- `adhd-communication`: trimmed SKILL.md by about 53% (6.0 KB to 2.8 KB, roughly 1,500 to 700 tokens) to cut per-use cost. Same rules; the principles table became a numbered list, and the examples were shortened. A blind A/B on 6 scenarios scored the trimmed version at parity with 1.1.0 (148 vs 149 of 150).

### [1.1.0] - 2026-11-17
#### Changed
- `adhd-communication`: everything that needs a reply (questions, decisions, confirmations) now goes in one `**Need from you (N)**` block as the last thing in the reply, with an item count in the label.
- `adhd-communication`: findings merge into the question they lead to, instead of being listed separately above a Questions block.
- `adhd-communication`: ask-sounding headings ("Things that need you", "Decisions", "Next steps" with choices) are banned outside the block; items needing no action go above it under `FYI, no action`.
- `adhd-communication`: the plan template's separate decisions table is replaced by the reply block.

### [1.0.0] - 2026-10-29
#### Changed (breaking)
- Plugin renamed from `adhd-communication` to `communication-style`, and its skill renamed from `no-walls` to `adhd-communication`. Uninstall `adhd-communication@rafas-marketplace` and install `communication-style@rafas-marketplace`.

#### Added
- `adhd-communication`: scope arguments: none (rest of session), `once` (next reply only), `off` (stop). Any other text is treated as the request.

#### Removed
- Legacy `commands/no-walls.md`, which duplicated the skill under the same command name with an outdated copy of its rules.

## adhd-communication (renamed to communication-style in 1.0.0)

### [0.2.1] - 2026-10-29
#### Changed
- `no-walls`: questions now go in a bold **Questions** block at the end of a reply, as a numbered list with key words bolded and a default where possible.

Earlier versions predate this changelog.
