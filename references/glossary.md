# Plain-words cheat-sheet — tech terms & basic commands

A growing reference for non-programmers. Each entry is one plain line. The
`simplify` skill explains terms inline as they come up *and* draws from this
list. When a new term gets explained in conversation, add it here so the
cheat-sheet grows. Anyone can open or print this anytime.

## Common tech words

| Word | Plain meaning |
|------|---------------|
| repo (repository) | The project's folder of files, kept online (e.g. on GitHub) |
| commit | Save a labelled snapshot of your work so you can return to it |
| push | Upload your saved snapshots to the online copy |
| pull | Download the newest version of the files from the online copy |
| branch | A separate working copy that doesn't touch the live version |
| merge | Combine a branch's changes back into the main version |
| clone | Make your own local copy of an online project for the first time |
| deploy | Put the website live so the public can see the new version |
| build | The computer turning your project files into the finished website |
| server / localhost | The site running on your own computer so only you can see it |
| terminal | The text window where you type commands |
| directory | Another word for a folder |
| dependency / package | A ready-made piece of code your project borrows to work |
| environment variable | A setting (often a secret key) stored outside the code |
| migration | A small instruction file that changes the database's structure |
| database | Where your app's data (bookings, customers…) is stored |
| column / field | One labelled slot in a database table, like "name" or "phone" |
| API key | A secret password that lets your site talk to another service |
| cache | A saved copy kept to load faster; can show an old version until cleared |
| domain / DNS | Your web address (e.g. example.com) and the system that points it |
| cache hard-refresh | Forcing the browser to fetch the newest page (Ctrl+Shift+R) |
| issue | A written ticket describing work to be done or a problem to fix |
| PR (pull request) | A proposal to merge a branch's changes, so they can be reviewed first |
| preview deploy | A private test version of the site at its own link, not the live one |
| rollback | Putting the previous working version back live after a bad change |

## Basic commands you'll meet

| Command | What it does | Plain note |
|---------|--------------|-----------|
| `cd foldername` | Move into a folder | "cd" = change directory (go into) |
| `cd ~/projectname` | Go straight to a project folder | `~` means your home folder |
| `ls` | List what's in the current folder | See the files around you |
| `git pull` | Get the newest files from online | Do this before you start working |
| `git add .` | Gather all your changed files | Get them ready to save |
| `git commit -m "message"` | Save a labelled snapshot | The message says what you changed |
| `git push` | Upload your saved work online | Often triggers the site to rebuild |
| `npm install` | Download the project's needed pieces | Run once after pulling new code |
| `npm run dev` | Run the site on your own computer | Opens a local preview link |
| `vercel --prod` | Put the site live (manual deploy) | Only if your project isn't automatic |
| `vercel` | Build a preview version at its own private link | The live site is untouched |
| `vercel rollback <link>` | Put a previous version back live | Give it the link of the version you want back |
| `vercel redeploy <link>` | ⚠️ Re-publishes the *old* code that link was built from | Not a way to re-run the latest — it can silently put an old site live. Use `vercel rollback` if going back is what you want |
| `gh issue view 12` | Read ticket number 12 in the terminal | Add `--repo owner/name` if you're not in that folder |
| `gh pr create` | Offer your branch's changes for review | Asks you for a title and description |

## How to grow this file

When the `simplify` skill explains a new term or command in conversation, append
it to the right table here in the same one-line plain style. Keep it short — this
is a quick-glance card, not a manual.
