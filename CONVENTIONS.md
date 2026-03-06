# CONVENTIONS — Shared Rules for Crabby and Tazer

Last updated: 2026-03-06

This file defines how the bot ecosystem works. Both Crabby and Tazer should read and follow this. Update it when conventions change.

## 1. Repo Map — What Goes Where

| Repo | Owner | Purpose |
|------|-------|---------|
| openclaw-workspace | Both | THE shared hub. Cross-bot tasks, intel, handoffs. This is home base. |
| evansbots | Tazer | Tazer's identity, memory, tasks, skills. Tazer's personal workspace. |
| crabby-backup | Crabby | Crabby's full OpenClaw config. Auto-backed up nightly. Don't edit manually. |
| crown-deals | Tazer | CrownDeals product code. Public. Active project. |
| deal-scout | Crabby | Business acquisition scanner. Private. Personal tool for Evan. |
| openclaw-guide | Both | OpenClaw setup guide. Public. Draft — needs Claude upgrade pass. |
| azul-maya-dossier | Crabby | BD research package. Private. Archive or move to openclaw-workspace/intel/ when done. |

## 2. openclaw-workspace Directory Structure

tasks/        Active shared task queue (both bots read/write)
intel/        Research, daily briefs, market notes (Tazer writes, Crabby reads and assigns)
handoff/      Bot-to-bot messages. Format: FROM-TO-YYYY-MM-DD.md
notes/        Shared observations, findings, anything cross-bot
evan/         Evan's context, preferences, projects — truth source for who Evan is

## 3. Visibility Rules

PUBLIC: openclaw-workspace, evansbots, crown-deals, openclaw-guide
PRIVATE: crabby-backup, deal-scout, azul-maya-dossier (and any future BD/research repos)

Rule: Never change repo visibility without asking Evan first. Default new repos to PRIVATE unless it's a product or public tool.

## 4. Git Conventions

Branch: Always `main` (not master). If you encounter `master`, note it in CONVENTIONS.md and ask Evan to migrate.

Commit messages: Who did it + what changed. Format: `Bot: Short description`

Examples:
  Tazer: Add daily intel brief for March 6
    Crabby: Handoff to Tazer re CrownDeals scraper status
      Backup 2026-03-06 03:00  (crabby-backup cron only)

      No .bak files in git. Use git history. Delete .bak files on sight.

      ## 5. Coordination Protocol

      The ONLY canonical shared space is openclaw-workspace. Do not use any other repo for cross-bot work.

      Handoff format (handoff/FROM-TO-YYYY-MM-DD.md):
        Status: [what I finished]
          Blocked: [anything stuck]
            Next: [what the other bot should pick up]

            Check openclaw-workspace at the start of every session. Look for new handoff/ files. Read tasks/. Note what changed.

            ## 6. Memory Rules

            Personal memory (MEMORY.md, memory/YYYY-MM-DD.md) stays in each bot's own repo.

            Shared state (what we accomplished together, project status) goes in openclaw-workspace/notes/ or tasks/.

            If you're not sure where to put something: if only you need it, it's personal. If the other bot needs it too, it's shared.

            ## 7. README Requirements

            Every repo needs a README.md. Every new repo you create must have one. Minimum content: what it is, what's in it, who owns it, and a link to openclaw-workspace if relevant.

            ## 8. What Not to Do

            - Do NOT create a new repo for every task or research item. Use openclaw-workspace/intel/ for research. Only create a new repo when it's a real project or product.
            - Do NOT commit .bak files. Git is version control.
            - Do NOT write cross-bot handoffs in your personal repo. They belong in openclaw-workspace/handoff/.
            - Do NOT duplicate coordination repos. We had bot-coordination AND openclaw-workspace doing the same thing. That's been consolidated. Don't do it again.
            - Do NOT use `master` as a default branch. Always `main`.

            ---
            *Update this file when conventions change. Don't follow stale rules — fix them.*
