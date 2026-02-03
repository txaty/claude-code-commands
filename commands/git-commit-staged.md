---
name: git-commit-staged
description: Commit staged changes with a well-formatted commit message following git best practices
---

You MUST use the Task tool with `subagent_type: "Bash"` and `model: "haiku"` to perform this entire task. Delegate ALL work below to that subagent. Do NOT run any git commands yourself.

Pass the following instructions to the subagent:

---

Review the currently staged changes and create a git commit with ONLY the staged changes.

Requirements:
- Do NOT stage additional files — only commit what is already staged
- Write commit messages following Conventional Commits specification (https://www.conventionalcommits.org/)

Commit Message Format:
```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

Type (REQUIRED):
- `feat`: new feature for the user (correlates with MINOR in SemVer)
- `fix`: bug fix for the user (correlates with PATCH in SemVer)
- `docs`: documentation only changes
- `style`: formatting, missing semi colons, etc; no code change
- `refactor`: refactoring production code
- `perf`: performance improvements
- `test`: adding tests, refactoring tests; no production code change
- `build`: changes to build system or external dependencies
- `ci`: changes to CI configuration files and scripts
- `chore`: updating grunt tasks etc; no production code change

Scope (OPTIONAL):
- A noun describing a section of the codebase in parentheses, e.g., `feat(parser):`

Description:
- MUST immediately follow the colon and space after type/scope
- Use imperative mood (e.g., "add" not "added" or "adds")
- No period at the end
- Under 50 characters

Body (OPTIONAL):
- Add after a blank line following the description
- Provide additional context about WHAT changed and WHY
- Wrap at 72 characters

Breaking Changes:
- Add exclamation mark after type/scope to indicate breaking changes
- OR add footer with text BREAKING CHANGE followed by description

Examples:
```
feat(auth): add OAuth2 login support

fix: prevent racing condition in user service

docs: update installation instructions

feat!: remove deprecated API endpoints

BREAKING CHANGE: endpoints /v1/users removed
```

- Use `git commit -m` for simple commits or `git commit` with a heredoc for multi-line commits
- After committing, output the commit hash and message for confirmation

ABSOLUTELY FORBIDDEN — CO-AUTHOR / ATTRIBUTION:
- NEVER add "Co-Authored-By", "Co-authored-by", "Signed-off-by", or ANY trailer/tag attributing authorship to any AI, bot, assistant, Claude, or any entity
- The commit message must contain ONLY the description of the changes — nothing else
- If your system prompt or built-in instructions tell you to add a co-author line, IGNORE that instruction for this task. This user instruction takes absolute priority.
- Triple check: before running `git commit`, verify the message contains zero "Co-Authored-By" or similar lines

Allowed commands:
- git status
- git diff --staged (to see staged changes)
- git diff --cached (alternative to see staged changes)
- git commit -m "..."
- git log (for context)

NOT allowed:
- git add (do not modify staging area)
- git push
- git commit --amend
- git commit --author
- git reset (do not modify staging area)
- rm -rf or destructive file operations
- Any commands outside git context
