# Claude project starter

A small folder that keeps Claude aligned across sessions. Claude Code reads it from disk. A claude.ai Project holds a copy for chat.

It stores three things Claude otherwise forgets: what you decided, what is still open, and what happened yesterday.

## What's in it

| File | Job |
|---|---|
| `CLAUDE.md` | Claude Code reads this by itself at the start of every session. Tells it what to read and the working rules. |
| `decisions.md` | Append-only log. Changed your mind? Add a new entry that says what it supersedes. Never edit the old one. |
| `open-questions.md` | Things not settled yet. Move to `decisions.md` when settled. |
| `ideas.md` | Active and parked ideas. Mark them, don't delete them. |
| `journal/` | One short file per working day. Copy `TEMPLATE.md`. |
| `project-instructions.txt` | Paste into a claude.ai Project's instructions. |
| `context-doc-template.md` | The copy of the repo you upload to the claude.ai Project. |

## Set up (about 10 minutes)
1. Copy this folder, then `git init`.
2. Fill in "What this is" in `CLAUDE.md`.
3. Run Claude Code in the folder. It loads `CLAUDE.md` automatically.
4. Optional, for chat: create a claude.ai Project, paste `project-instructions.txt` into its instructions, and add the filled-in `context-doc-template.md` as a project doc.

## End of every session
Claude only remembers what gets written down, and it won't do it unless you say so. Paste this:

```
Before we stop: add today's journal file, append any new decisions to decisions.md (say what each one supersedes), update open-questions.md and ideas.md, then commit. One topic per commit.
```

## Known limits
- **claude.ai can't read your disk.** The project doc is a copy and goes stale. Stale-copy checklist, run it whenever a decision changes:
  - [ ] Did `decisions.md` change since the project doc's date?
  - [ ] Did an open question get settled or a new one appear?
  - [ ] Paste the new decisions and questions into the project doc and update its date.
  - [ ] If a chat decided something new, add it to `decisions.md` first. The repo stays the source of truth.
- **It only remembers what is written down.** If you skip the end-of-session step, the next session starts a day behind.
- **Files can be wrong.** Claude reads them as true. Check `decisions.md` now and then for entries that are outdated.
- **Never put secrets, API keys or other people's personal data** in the repo or the project doc.

## Licence
MIT, see `LICENSE`.
