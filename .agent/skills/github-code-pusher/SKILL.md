---
name: github-code-pusher
description: Pushes local code to a GitHub repository. Use when the user wants to version control their current project or share it on GitHub.
---

# GitHub Code Pusher

This skill provides a secure and structured way to push local project code to a new or existing GitHub repository.

## When to use this skill
- Use this when the user says "upload my code to GitHub", "create a repo for this", or "sync my changes with GitHub".
- Useful for initializing version control on a fresh project.

## How to use it

Follow these steps to push code to GitHub:

1.  **Check for Local Git Repository:**
    - Use `run_command` with `git status` to check if the current directory is already a git repo.
    - If not initialized, run `git init`.

2.  **Determine Repository Destination:**
    - Ask the user if they want to push to an **existing** repository or create a **new** one.
    - If **new**, use `mcp_github-mcp-server_create_repository` to create it on their account.
    - If **existing**, ask for the repository owner and name.

3.  **Stage and Commit Changes:**
    - Use `run_command` with `git add .` to stage all files (respecting `.gitignore`).
    - Use `run_command` with `git commit -m "Initial commit"` (or a descriptive message provided by the user).

4.  **Configure Remote:**
    - Add the remote origin using `run_command`: `git remote add origin https://github.com/<owner>/<repo>.git`.
    - If origin already exists, verify it with `git remote -v`.

5.  **Push Code:**
    - Identify the current branch name (usually `main` or `master`).
    - Use `run_command` to push: `git push -u origin <branch-name>`.

6.  **Verify:**
    - Confirm the push was successful.
    - Provide the user with the GitHub URL of the repository.

## Best Practices
- **Never push sensitive data:** Check the root for `.env` files or API keys. Remind the user to add these to `.gitignore`.
- **Handle authentication:** If `git push` fails due to credentials on Windows, remind the user to use GitHub Desktop or the Git Credential Manager.
- **Branch Naming:** Prefer `main` as the default branch name.
- **Atomic Commits:** If the project is large, suggest making smaller, descriptive commits instead of one giant upload.
