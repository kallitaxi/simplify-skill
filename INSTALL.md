# How to install the simplify skill

The goal: get the `simplify` folder to live at **`~/.claude/skills/simplify`**
on the computer that runs Claude Code. Below: how to find that folder, then two
ways to put the skill in it.

---

## First: how to find your skills folder

`~/.claude/skills/` is a folder in your home directory. If it doesn't exist yet,
the install commands below create it. Here's how to open it to look inside.

### Mac or Linux

| Step | Do this | Where |
|------|---------|-------|
| 1 | Open a terminal | — |
| 2 | Type `open ~/.claude/skills` (Mac) or `xdg-open ~/.claude/skills` (Linux), then Enter | Terminal |

### Windows with WSL (Claude running inside Ubuntu/Linux on Windows)

The skills folder lives on the **Linux side**, which normal Windows browsing
hides. Reach it through File Explorer:

| Step | Do this | Where |
|------|---------|-------|
| 1 | Open **File Explorer** (yellow folder icon) | Windows |
| 2 | Click in the **address bar** at the top | File Explorer |
| 3 | Paste `\\wsl.localhost\Ubuntu\home\YOURNAME\.claude\skills` and press Enter | Address bar |
| 4 | You now see your skill folders | File Explorer |

Swap `Ubuntu` for your distro name if different, and `YOURNAME` for your Linux
username. To find both: in the terminal type `echo $WSL_DISTRO_NAME` and `whoami`.

Tip: drag that folder into **Quick access** (left sidebar) once — then it's a
single click forever.

> Why hidden: Linux (where Claude lives) and Windows are two separate worlds on
> the same PC. The `\\wsl.localhost\...` address is the bridge between them.

---

## Way 1 — from the `simplify.skill` file (easiest, no GitHub needed)

The `.skill` file is just a zip in disguise.

| Step | Do this | Where |
|------|---------|-------|
| 1 | Get the `simplify.skill` file onto the computer (e.g. in Downloads) | — |
| 2 | Type `mkdir -p ~/.claude/skills` then Enter | A terminal |
| 3 | Type `unzip ~/Downloads/simplify.skill -d ~/.claude/skills/` then Enter | Same terminal |
| 4 | Close Claude Code and open it again | Same terminal |
| 5 | In Claude, type "use the simplify skill" to check it loaded | Claude chat |

No terminal / can't unzip on the command line? Rename `simplify.skill` to
`simplify.zip`, double-click to unzip, then drag the resulting `simplify` folder
into your skills folder (found using the section above).

## Way 2 — from the GitHub repo

The repo is public — anyone can install it, no account or permission needed.

| Step | Do this | Where |
|------|---------|-------|
| 1 | Type `mkdir -p ~/.claude/skills` then Enter | A terminal |
| 2 | Type `git clone https://github.com/kallitaxi/simplify-skill.git ~/.claude/skills/simplify` then Enter | Same terminal |
| 3 | Close Claude Code and open it again | Same terminal |
| 4 | In Claude, type "use the simplify skill" to check | Claude chat |

---

## What the words mean

- **terminal** — the text window where you type commands
- **unzip** — unpack a zipped (compressed) file
- **clone** — make your own copy of an online project onto your computer
- **`~`** — your home folder (a shortcut, so you don't type the full path)
- **WSL** — "Windows Subsystem for Linux"; Linux running inside Windows
- **distro** — which flavour of Linux you run (e.g. Ubuntu)

## Which to give people

- **Not technical?** Send the `simplify.skill` file and Way 1 (with the
  double-click-and-drag fallback).
- **Already use git, has repo access?** Way 2.

## Use it once installed

- Type `/simplify`, or "simplify this", "give me steps", "in plain English".
- Or just ask any how-to question — it triggers on its own when an answer would
  otherwise hand you jargon or a command with no home.
