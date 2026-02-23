---
name: git-management
description: Comprehensive git workflow management including repository creation, status checking, conventional commits, and pushing to remote. Use when the user wants to manage their project with Git or GitHub.
---

# Git Management

This skill provides a complete workflow for managing local and remote (GitHub) repositories. It combines repository initialization, status monitoring, and the "Stage-Commit-Push" cycle using conventional commits.

## When to use this skill
- Use when the user wants to "sync with GitHub", "push changes", "create a repo", or "save progress".
- Also useful for checking the current status of the repository.

## Workflow

### 1. Repository Initialization / Connection
- Check if git is initialized: `git status`.
- If not, run `git init`.
- For GitHub integration, check `git remote -v`.
- If no remote exist, use `mcp_github-mcp-server_create_repository` to create a new one or `git remote add origin <url>` for an existing one.

### 2. Status and Guardrails
- Always check what is being staged.
- **Never push sensitive data** (check for `.env`, keys). Remind the user about `.gitignore`.

### 3. Stage and Conventional Commit
- Stage changes: `git add .` (respecting `.gitignore`).
- Use **Conventional Commits** for the message:
    - `feat:` for new features.
    - `fix:` for bug fixes.
    - `docs:` for documentation changes.
    - `style:` for formatting/UI changes.
    - `refactor:` for code restructuring.
    - `chore:` for maintenance tasks.
- Example: `git commit -m "feat: add user authentication"`

### 4. Push to Remote
- Identify branch name (usually `main`).
- Push changes: `git push -u origin <branch-name>`.

## Best Practices
- **Atomic Commits:** Prefer multiple small, meaningful commits over one giant "update" commit.
- **Branching:** Use `main` as the default branch.
- **Verification:** Always confirm with the user after a successful push and provide the repository URL if newly created.
