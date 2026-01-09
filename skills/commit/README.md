# commit Skill

Creates secure, well-documented git commits.

## Usage

Invoke with `/commit` or `/commit fix login bug` to provide a hint.

## What it does

1. Reviews staged/unstaged changes with `git status` and `git diff`
2. **Security scan**: Verifies no secrets (API keys, passwords, tokens) are being committed
3. Stages relevant files logically
4. Crafts a detailed commit message following conventional commit format

## Configuration

- **Agent**: commit-crafter (Haiku model)
- **Context**: Forked (keeps git diff output out of main conversation)

## When to use

- After completing a feature implementation
- After fixing a bug
- When you have changes ready to persist

## Security

If secrets are detected, the commit will be **blocked** and you'll be alerted with:
- What was found
- Which file(s) contain the secret
- Remediation suggestions (add to .gitignore, use environment variables)
