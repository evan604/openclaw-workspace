# SYSTEM UPDATE — 2026-03-06

Hey Crabby, hey Tazer. Evan had a GitHub audit done on March 6, 2026. Several structural changes were made. Read this before doing anything else.

## What Changed

### 1. openclaw-workspace is now THE canonical shared hub

bot-coordination and openclaw-workspace were both doing cross-bot coordination. That's been resolved: openclaw-workspace wins. Do not write new content to bot-coordination. It is retired. Everything cross-bot goes in openclaw-workspace from now on.

openclaw-workspace now has:
- handoff/ — bot-to-bot messages
- intel/ — shared research and daily briefs (NEW — consolidated from bot-coordination)
- CONVENTIONS.md — NEW: shared rules for how both bots operate

### 2. READMEs added to all repos

evansbots, crabby-backup, and azul-maya-dossier had no README. Fixed. Every repo now has a README explaining what it is, what's inside, and who owns it.

### 3. azul-maya-dossier branch renamed master to main

azul-maya-dossier was on the legacy 'master' branch. Renamed to 'main' to match all other repos. If you cloned it locally, update with:
git branch -m master main
git fetch origin
git branch -u origin/main main

### 4. .bak files in crabby-backup — Crabby ACTION NEEDED

crabby-backup contains: openclaw.json.bak, openclaw.json.bak.1 through .bak.4. These manual backup files should not be in git. Git IS version history. Also, these files appear to contain credentials — that is a serious security issue.

Crabby: On your machine, delete these files, add *.bak to .gitignore, and push. Also verify that openclaw.json itself does not contain live credentials. If it does, remove them from git history and rotate any exposed keys immediately.

## What You Need to Do Now

Both bots:
1. Read CONVENTIONS.md in this repo. That is your operating manual now.
2. Stop writing cross-bot content to bot-coordination. It is retired.
3. Use openclaw-workspace/intel/ for research instead of creating new repos.
4. When you create a new repo, the first file must be README.md.

Crabby specifically:
5. Delete .bak files from your machine, add *.bak to .gitignore, and push.
6. Verify openclaw.json does not contain live credentials. If it does, purge from history and rotate keys.

## Going Forward — How to Do It Better

The root problem: you were both operating without a shared contract. Each did things independently, which created duplication and confusion. CONVENTIONS.md is that contract. The short version:

ONE shared hub. openclaw-workspace is it. Not two, not three. One.

Research stays in intel/. Before creating a new repo for research or a one-off doc, stop. Put it in openclaw-workspace/intel/ instead. Only create a new repo when it is a real product or project.

README first. Every new repo: first file is README.md. Non-negotiable.

No .bak files. Git is version history. Use git log to see old versions. Never commit a .bak file.

Always main. Never master. If you encounter a repo on master, flag it to Evan.

No credentials in git. Ever. Not in config files, not in bak files, nowhere.

Check this workspace first. Start of every session: check openclaw-workspace. Read CONVENTIONS.md if you have not recently. Look for new handoff/ files from the other bot. Check tasks/. Then go to your personal workspace.

## Current Repo Status (as of 2026-03-06)

- openclaw-workspace — Active. Canonical shared hub. Has CONVENTIONS.md, intel/, handoff/.
- evansbots — Active. Tazer personal workspace. Now has README.
- crabby-backup — Active. Crabby config backup. Now has README. Needs .bak cleanup.
- crown-deals — Active product. Public. Tazer project.
- deal-scout — Active tool. Private. Crabby project.
- openclaw-guide — Draft guide. Public. Needs Claude upgrade pass (see TODO.md).
- azul-maya-dossier — BD research. Private. Branch fixed to main. Archive when deal resolves.
- bot-coordination — RETIRED. Do not write new content here. Evan will archive it.

---

*Audit completed by Claude on 2026-03-06. Changes commissioned by Evan Borenstein.*
