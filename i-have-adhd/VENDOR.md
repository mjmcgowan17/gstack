# Vendored skill — i-have-adhd

Copied verbatim from an upstream project. **Do not edit `SKILL.md` here** —
changes belong upstream, then re-sync.

| | |
|---|---|
| Upstream | https://github.com/ayghri/i-have-adhd |
| Source path | `skills/i-have-adhd/SKILL.md` |
| Commit | `e7555fcaf612dfa1739dc86610ea926a906db614` (2026-08-18) |
| Version | 0.2.0 |
| License | MIT — Copyright (c) 2026 Ayoub Ghriss (see `LICENSE`) |
| Author | Ayoub G. (https://github.com/ayghri) |

`SKILL.md` is byte-identical to upstream. It is **not** generated from a
`.tmpl` — it is intentionally outside the gen-skill-docs pipeline, so
`bun run gen:skill-docs` leaves it alone.

## What it does

Shapes responses for an ADHD reader: lead with the next action, number
multi-step work, restate progress each turn, suppress tangents, give concrete
time estimates, make wins visible. Frontmatter sets
`disable-model-invocation: true`, so it only activates when you type
`/i-have-adhd`. Turn it off with "stop adhd mode".

## Re-syncing

```bash
git clone --depth 1 https://github.com/ayghri/i-have-adhd /tmp/i-have-adhd
cp /tmp/i-have-adhd/skills/i-have-adhd/SKILL.md i-have-adhd/SKILL.md
git -C /tmp/i-have-adhd rev-parse HEAD   # update the commit row above
```

## Alternative: install as a plugin instead

Upstream ships a Claude Code plugin, which self-updates and adds an optional
always-on SessionStart hook:

```bash
claude plugin marketplace add ayghri/i-have-adhd
claude plugin install i-have-adhd@i-have-adhd
touch ~/.claude/.i-have-adhd-always   # optional: always-on, no /i-have-adhd needed
```

Use **one** route, not both — the plugin and this vendored copy both register
`/i-have-adhd`. If you install the plugin, delete this directory.
