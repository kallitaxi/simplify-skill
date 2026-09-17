# simplify — a Claude skill for plain-language, do-able instructions

A Claude Code skill that turns any technical how-to into something a
**non-programmer** can act on immediately: plain words, numbered one-at-a-time
steps in a table that says exactly *where* each step happens, every tech word
explained in one line, links shown as clickable links, and a saved local copy
of anything you'll read.

Built for people who think in structures and processes but don't write code —
project managers, business owners, ops leads, domain experts.

## What it does (the seven rules)

1. **Numbered steps, one at a time** — step 2 only after step 1 is done.
2. **A "Where" column** — new terminal / same terminal / browser / which folder.
3. **Plain words, no jargon.**
4. **Every tech word explained in one line**, plus a growing cheat-sheet
   (`references/glossary.md`).
5. **Links shown as clickable links**, on their own line.
6. **Short by default** — detail on request.
7. **A local copy** of any document you'll read, saved where you choose.

## Install (for a recipient)

| Step | Do this | Where |
|------|---------|-------|
| 1 | Get the `simplify.skill` file (or this folder) | — |
| 2 | Put the `simplify` folder into your Claude skills folder: `~/.claude/skills/simplify` | A terminal |
| 3 | Start (or restart) Claude Code | A terminal |
| 4 | Check it loaded — ask Claude to "use the simplify skill" | Claude chat |

The `.skill` file is just a zip of this folder. Unzip it into `~/.claude/skills/`
if you have the packaged version.

## Use it

- Type `/simplify` or "simplify this", "give me steps", "in plain English".
- Or just ask any how-to question — it triggers on its own when an answer would
  otherwise hand you jargon or a command with no home.

## Files

- `SKILL.md` — the skill itself.
- `references/glossary.md` — plain-words cheat-sheet of tech terms and basic
  commands; grows as new terms come up.
