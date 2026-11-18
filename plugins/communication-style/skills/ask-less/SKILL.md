---
name: ask-less
description: Adds "act on reasonable defaults, ask only when necessary" rules to the current project's CLAUDE.md, so Claude stops interviewing you before working. Use when the user says Claude asks too many questions, wants it to just proceed, or runs /ask-less. Argument "global" writes to ~/.claude/CLAUDE.md instead.
---

# Ask Less

Add the block below to CLAUDE.md so future sessions act on stated assumptions instead of asking. This changes instructions only; it never changes permission settings.

## Steps

1. **Pick the file.** Default: `./CLAUDE.md` at the repo root (or `./.claude/CLAUDE.md` if that's the one in use). With `global`: `~/.claude/CLAUDE.md`, and warn in your report that it applies to every project. Create the file if it doesn't exist.
2. **Check if it's shared.** If the file is tracked in git (`git ls-files --error-unmatch <file>` succeeds), say in your report that committing it changes Claude's behavior for everyone on the repo.
3. **Make it idempotent.** If the file already has `<!-- ask-less:start -->` … `<!-- ask-less:end -->`, replace what's between the markers. Otherwise append the block at the end.
4. **Handle conflicts.** Search the file for lines that push toward asking ("ask before guessing", "always confirm", "ask if unsure", all-caps MUST/NEVER rules about asking). They weaken the block, so:
   - **File tracked in git:** remove those lines, since git can restore them. List what you removed in your report.
   - **Not tracked:** don't remove them; list them with line numbers for the user to remove.
5. **Write the block** exactly as below.
6. **Report** in a few lines: which file changed, whether it's shared, the conflicts removed or listed, and that the change applies to new sessions.

## The block

```markdown
<!-- ask-less:start -->
## Acting vs. asking
- When details are missing, make a reasonable assumption, state it in one line, and proceed.
- Use tools (read files, search, run commands) to answer your own questions before asking me.
- Ask only when the result would be wrong or unusable without my answer, or before any action that is destructive, irreversible, or reaches beyond this repo: deleting data, overwriting uncommitted work, force-pushing, deploying, sending messages, changing files outside the repo or global config, installing packages, or spending money or API quota.
- If an action is reversible and within what I asked for, do it instead of asking "Want me to…?".
- Don't ask about optional extras; mention them in one "Could also:" line instead.
- When you do ask, put every question at the end of the reply, numbered, each with the default you'll use if I don't answer.
<!-- ask-less:end -->
```

## Why it's worded this way

Newer Opus models follow instructions literally: rules written as judgment ("only when the result would be wrong") work better than counts or all-caps bans, which over-trigger. The block keeps the real reasons to ask, risky or irreversible actions, so Claude doesn't guess on those. There is deliberately no question timeout: an unanswered question about a risky action should stop the work, not let it proceed.
