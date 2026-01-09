# Commit Crafter Plugin

A Claude Code plugin for creating secure, well-documented git commits.

## Features

- **Security scanning**: Automatically detects secrets (API keys, passwords, tokens) before committing
- **Conventional commits**: Follows the conventional commit format (feat, fix, docs, etc.)
- **Context isolation**: Runs in a forked context to keep git diff output out of your main conversation
- **Smart staging**: Groups related changes and suggests splitting large commits

## Installation

```bash
# From local directory
claude plugin install ~/projects/claude-commit-plugin

# From git repository (once published)
# claude plugin install github:username/claude-commit-plugin
```

## Usage

### Via slash command
```
/commit
/commit fix authentication bug
```

### Via natural language
Just ask Claude to commit your changes:
- "commit these changes"
- "create a commit for the login fix"

## What it does

1. **Reviews changes** - Runs `git status` and `git diff` to understand modifications
2. **Security scan** - Checks for secrets, API keys, passwords, tokens
3. **Blocks if secrets found** - Alerts you with specific remediation steps
4. **Stages files** - Groups related changes logically
5. **Crafts message** - Creates a detailed commit message explaining WHY

## Commit Message Format

```
<type>: <summary in imperative mood>

<body explaining WHY the changes were made>
- What problem does this solve?
- Why was this approach chosen?

<footer with references>
```

### Types
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation only
- `style`: Formatting, no code change
- `refactor`: Code restructuring
- `test`: Adding tests
- `chore`: Maintenance tasks

## Configuration

The plugin uses these defaults:
- **Model**: Haiku (fast and cost-effective)
- **Context**: Forked (isolated from main conversation)

## License

MIT
