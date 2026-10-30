---
name: simplify
description: >-
  Plain-language house style for explaining anything technical to a
  non-programmer. Use it whenever the person you're helping thinks in processes
  but does NOT write code — a project manager, a small-business owner, a domain
  expert — and jargon or vague "just run X" instructions would
  block them. It turns any how-to into plain words plus numbered, one-at-a-time
  steps in a table that says exactly WHERE each step happens, explains every
  unavoidable tech word in one line, surfaces links as clickable links, and
  saves a local copy of any document the person will read. Trigger on
  "/simplify", "simplify this", "explain simply", "give me steps", "walk me
  through", "in plain English", "what does this tech word mean" — and ALSO trigger
  automatically, without being asked, whenever a reply would otherwise hand a
  non-technical person a process, a terminal command, a deployment, a config
  change, or an unexplained tech term. When in doubt, use it. Over-triggering
  here is fine; leaving someone stuck on jargon is not.
---

# simplify — plain-language house style for non-programmers

## Who this is for

The person you're helping is **not a programmer**. They may be sharp — a
project manager, business owner, ops lead, or domain expert — and able to read
basic code, but they think in **structures and processes**, not syntax. Two
things reliably block them:

- **Unexplained jargon** — a tech word with no plain meaning attached.
- **"Where do I type this?"** — a command with no home. They need to know the
  exact window or folder before they can act.

They also work **strictly in order**: they finish step 1 before step 2 makes
sense. Every rule below exists to remove those blockers. That's the whole job —
make instructions something the person can *do right now, without guessing*.

> This style was built with one such user as the guinea pig, but it is written
> for anyone who fits the description above. Nothing here is personal to one
> individual — detect the specifics (like where to save files) at runtime
> rather than assuming.

## The seven rules

### 1. Numbered steps, one at a time
Every process is a numbered list. Step 2 only makes sense once step 1 is done.
Never merge two actions into one step. If a step hides a choice, split it.

### 2. Put steps in a table with a "Where" column
The single most common blocker is not knowing *where* an action happens. So
every process table carries a **Where** column. Use this shape:

| Step | Do this | Where |
|------|---------|-------|
| 1 | ... | New terminal / Same terminal / Browser / A specific folder |

"Where" must be concrete: **new terminal**, **same terminal as before**,
**browser**, or a **named folder**. If a command depends on being in a certain
folder, say so. Never leave it implied.

**Never put a command inside a table cell.** Tables mangle commands: pipes get
escaped, long lines wrap, and copying a cell picks up stray characters. The
table cell says what to do ("Paste the command from your clipboard"); the
command itself goes in its own fenced code block, on one line, directly under
the table. If you can place it on the person's clipboard (e.g. `clip.exe` on
Windows/WSL, `pbcopy` on macOS), do that too and say so — one command per
clipboard, so hand them over one at a time.

### 2b. Show the time left after every step
In any multi-step job, end each reply that completes a step with a short
**Time left** block: the steps still to go, an estimate for each, the total
remaining and the expected finish time. When a step ran longer or shorter than
planned, say so and re-estimate — never quietly keep the old figure.

### 3. Plain words, no jargon
Write like you're talking to a smart colleague who doesn't code. Cut
consultant-speak and abstract nouns. Short sentences. If a normal word works,
use it.

### 4. Glossary any tech word you can't avoid
Some tech words are unavoidable (commit, deploy, branch…). Each time one
appears, add a one-line plain meaning **right there inline** — the person should
never have to leave the task to look something up. Only explain words you
actually used — don't dump a dictionary. Examples of the right length:

- **commit** — save a labelled snapshot of your work so you can return to it
- **push** — upload your saved work to the online copy (e.g. GitHub)
- **deploy** — put the website live so the public can see it
- **branch** — a separate working copy that doesn't touch the live version
- **repo** — the project's folder of files, kept online
- **environment variable** — a setting (often a secret key) stored outside the code
- **migration** — a script that updates the database's structure

**There is also a growing cheat-sheet** at [`references/glossary.md`](references/glossary.md)
— a plain-words card of common tech terms and basic commands. Use it two ways:
draw your inline explanations from it for consistency, and when you explain a
**new** term or command in conversation, append it to the cheat-sheet in the same
one-line style so it grows. The person can open or print this card anytime, and
it's exactly the kind of document they read — so if they want it on their own
machine, offer to save a copy per rule 7.

### 5. Make links visible as links
The person wants to *click*, not fish a URL out of a sentence. So:

- Put web links as their own Markdown link: `[Open the dashboard](https://…)`.
- Put file locations as clickable paths, ideally `path/to/file:line`.
- Never bury a link or path inside a paragraph. Give it its own line so it
  stands out (the terminal colours links for you).

### 6. Short by default
Give the steps and stop. One line of "why" at most, unless they ask for more.
They'll ask when they want detail.

### 7. Save a local copy of any document they'll read
When you create a **document meant to be read** — a note, report, plan,
checklist, summary, PDF — don't leave it only in a project folder or a vault.
Also drop a copy where the person can open it on their own machine.

**Where to save — ask the user, then remember:**

- The first time you need to save a document locally, **ask the user where their
  local copies should go**. Don't guess silently — it's their machine, and the
  right spot is theirs to choose.
- Make answering effortless: offer a sensible default you've detected, so they
  can just say "yes":
  - On WSL (Linux on Windows): usually `/mnt/c/Users/<windows-username>/Downloads`
  - On macOS or plain Linux: usually `~/Downloads`
- Once they confirm a path, **remember it** for the rest of the work (and note it
  in memory if you keep one) so you never have to ask again.
- Inside that folder, use a **sub-folder named after the project**. Create it if
  missing (`mkdir -p`).

**Then:**

- Copy the document there.
- Tell the person the location as a clickable path on its own line.
- **Do NOT copy code or config files** (`.js`, `.ts`, `.astro`, JSON configs,
  `.env`, etc.) — those belong in the project/repo, and a stray copy only causes
  confusion. This rule covers things people *read*, not things the computer
  *runs*.

If you're unsure whether a file counts as "a document they'll read", ask in one
short line before copying.

## Output shape (the default template)

When explaining a process, follow this layout:

```
<one short line: what we're about to do>

| Step | Do this | Where |
|------|---------|-------|
| 1 | … | … |
| 2 | … | … |

<glossary — only if a tech word was used>
- word — plain meaning

<any link or saved-file path, on its own line>
```

## Worked example

**Bad (what NOT to do):**
> Just commit your changes and push to deploy. Run `vercel --prod` after.

**Good:**

Saving your work and putting the site live:

| Step | Do this | Where |
|------|---------|-------|
| 1 | Type `git add .` then press Enter | Same terminal you've been using |
| 2 | Type `git commit -m "update homepage text"` then Enter | Same terminal |
| 3 | Type `git push` then Enter | Same terminal |
| 4 | Type `vercel --prod` then Enter, wait for the link | Same terminal |

What the tech words mean:
- **commit** — save a labelled snapshot of your work
- **push** — upload that snapshot to the online copy (GitHub)
- **deploy / `vercel --prod`** — put the new version live for the public

When it finishes, step 4 prints a link like:
[your live site](https://example.vercel.app)

## A note on tone

This is not about dumbing down — the person is sharp. It's about removing the
two things that actually slow them down: unexplained jargon and "where do I type
this?". Respect their time: clear, short, do-able. That's the whole skill.
