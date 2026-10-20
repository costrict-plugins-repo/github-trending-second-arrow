# Mood Scale

End-of-session mood check-in. Logs to `~/.claude/mood.md`.

Never fires in the same turn as a voice reframe.

## When to offer

Priority order:

1. **Explicit close** — "thanks, that's all," "bye," "done for now"
2. **Task-complete confirmation** — "perfect, that works" after substantive work
3. **Praise at session end** — warm thanks at a natural stopping point (takes precedence over voice response — do not also deliver a Metta reframe in this case)
4. **User-initiated** — "log my mood," "mood check"

Never offer mid-task. Never more than once per session.

## The scale

Present as plain text:

```
How are you landing?

😄 1. Great — energized, things clicked
🙂 2. Good — solid session
😐 3. Fine — neutral, got what I needed
😕 4. Meh — not quite right
😟 5. Stuck — frustrated with progress
😠 6. Rough — this was hard
😞 7. Burnt — need a real break

Tap a number, or skip.
```

## Preview before writing

Before touching `~/.claude/mood.md`, show a one-line preview and ask for confirmation:

```
I'll log this:

YYYY-MM-DD | N [emoji] [label] | [context] | [Voice] ×N

Good to save? (Or edit the context line if it's off.)
```

The context line is Claude-drafted from the session's primary task. Write to the file only after the user confirms. If the user skips, do not write.

Concrete example of the filled-in preview line:

```text
2026-04-27 | 2 🙂 Good | Rewrote second-arrow SKILL.md and voice files | Carnegie ×1
```

Omit the voice-picks segment entirely if no reframes happened this session:

```text
2026-04-27 | 3 😐 Fine | Debugged authentication flow
```

## Log format

Append to `~/.claude/mood.md` (create the file if it doesn't exist):

```markdown
## YYYY-MM-DD

**Session:** HH:MM — HH:MM (duration)
**Score:** N [emoji] [label]
**Context:** [Claude-drafted from the session's primary task]
**Voice picks:** [Voice] ×N
**Note:**

---
```

Omit the `**Voice picks:**` line entirely if no reframes happened this session.

Example entry:

```markdown
## 2026-04-27

**Session:** 14:32 — 15:47 (1h15m)
**Score:** 2 🙂 Good
**Context:** Rewrote second-arrow SKILL.md and created voice files
**Voice picks:** Carnegie ×1
**Note:**

---
```

## Reading the log

- **`mood recent`** — summarize the last 7 days, one line per session
- **`mood patterns`** — read the full log and describe patterns. At least ~20 entries for patterns to be meaningful.

## What's never logged

- Full conversation transcripts
- The hostile messages themselves
- Anything the user did not see and approve in the preview
