# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repo Is

A collection of custom slash commands (`.md` files) for Claude Code, installed by copying into `~/.claude/commands/` (global) or `.claude/commands/` (project-specific).

## Repository Structure

- `commands/` - Markdown files that define Claude Code slash commands. Each file uses YAML frontmatter (`name`, `description`) followed by the prompt instructions.

## Command Design Patterns

Commands in this repo follow these conventions:

- **Delegate to subagents**: Commands use the Task tool with `subagent_type: "Bash"` and `model: "haiku"` to perform work, keeping the main agent context clean.
- **Conventional commits**: Commit messages use conventional commit format, imperative mood, under 50 chars first line, body wrapped at 72 chars.
- **No co-author tags**: Commands explicitly forbid `Co-Authored-By`, `Signed-off-by`, or any AI attribution trailers in commit messages.
- **Safety constraints**: Commands restrict allowed git operations (no `push`, `--amend`, `--hard` reset, or destructive file ops).

## Adding New Commands

Create a new `.md` file in `commands/` with this structure:

```markdown
---
name: command-name
description: Brief description
---

Instructions for Claude Code...
```
