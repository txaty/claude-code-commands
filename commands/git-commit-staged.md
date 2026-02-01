---
name: git-commit-staged
description: Commit staged changes with a well-formatted commit message following git best practices
---

Review the currently staged changes and create a git commit with ONLY the staged changes.

Requirements:
- Do NOT stage additional files - only commit what is already staged
- Write a clear, concise commit message following conventional commit format when appropriate
- First line: imperative mood, under 50 characters, no period
- If needed, add a blank line then a detailed body (wrap at 72 characters)
- Focus on WHAT changed and WHY, not HOW
- Do NOT add co-author tags or any author attribution
- Use `git commit -m` for simple commits or `git commit` with message file for complex ones

Allowed commands:
- git status
- git diff --staged (to see staged changes)
- git diff --cached (alternative to see staged changes)
- git commit -m "..."
- git commit -F [message file]
- git log (for context)

NOT allowed:
- git add (do not modify staging area)
- git push (user should push manually)
- git commit --amend (modifying history should be explicit)
- git commit --author (no author manipulation)
- git reset (do not modify staging area)
- rm -rf or destructive file operations
- Any commands outside git context

After committing, show the commit hash and message for confirmation.
