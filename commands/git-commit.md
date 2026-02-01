---
name: git-commit
description: Commit all changes with a well-formatted commit message following git best practices
---

Review all changes in the repository and create a git commit with ALL changes.

Requirements:
- Use `git add -A` to stage all changes
- Write a clear, concise commit message following conventional commit format when appropriate
- First line: imperative mood, under 50 characters, no period
- If needed, add a blank line then a detailed body (wrap at 72 characters)
- Focus on WHAT changed and WHY, not HOW
- Do NOT add co-author tags or any author attribution
- Use `git commit -m` for simple commits or `git commit` with message file for complex ones

Allowed commands:
- git status
- git diff
- git add -A
- git add [specific files]
- git commit -m "..."
- git commit -F [message file]
- git log (for context)

NOT allowed:
- git push (user should push manually)
- git commit --amend (modifying history should be explicit)
- git commit --author (no author manipulation)
- git reset --hard (destructive operations)
- rm -rf or destructive file operations
- Any commands outside git context

After committing, show the commit hash and message for confirmation.
