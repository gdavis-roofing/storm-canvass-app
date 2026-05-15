# storm-canvass-app — editing rules

BEFORE editing index.html:
- Run `git pull --rebase` first to ensure local is current
- Edit in place via Claude Code only
- Never paste full-file responses from AI canvas/chat over index.html — that's how the May 14 regression happened

AFTER committing:
- Run `git diff --stat HEAD~1`
- If an "Add X" commit shows >100 deletions, it's a stale-base commit. Reset and try again before pushing.

Deploy:
- `git push origin main` (Vercel auto-deploys on push)
- Verify on https://storm-canvass-app.vercel.app/ in incognito before assuming success

History:
- ba9090c (May 14) was a stale-base commit that wiped Fort Smith storm, STL storm, WIND tab, role picker, and progress bars. The claimed "Reports tab" was never actually implemented. Restored as b00f6df from 490da08.
