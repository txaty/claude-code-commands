# Claude Code Commands

Custom commands for [Claude Code](https://claude.com/claude-code) to enhance your development workflow.

## Installation

### Global (all projects)

```bash
cp commands/*.md ~/.claude/commands/
```

### Project-specific

```bash
mkdir -p .claude/commands
cp commands/*.md .claude/commands/
```

## Commands

### `/git-commit`

Stages and commits all changes with a well-formatted commit message following git best practices.

**Usage:** `/git-commit`

**Features:**
- Stages all changes (`git add -A`)
- Conventional commit format
- Imperative mood, <50 chars first line
- No co-author tags
- Safe: won't push or amend

### `/git-commit-staged`

Commits only staged changes with a well-formatted commit message.

**Usage:** `/git-commit-staged`

**Features:**
- Commits staged changes only
- Does not modify staging area
- Same commit message standards
- Safe: won't push or amend

## Command Format

Commands use Markdown with YAML frontmatter:

```markdown
---
name: command-name
description: Brief description
---

Instructions for Claude Code...
```

## License

MIT
