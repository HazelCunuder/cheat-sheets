# Git Cheat Sheet

Git is a distributed version control system that allows developers to track changes in their code, collaborate efficiently, and manage project versions. Mastering Git commands can streamline development workflows and improve code management.

## Table of Content

* [Basic Commands](#basic-git-commands)
* [Branching and merging](#branching-and-merging)
* [Remote Repositories](#remote-repositories)
* [Undoing Changes](#undoing-changes)
* [Git Shortcuts](#git-shortcuts)
* [Common Git Problems and Solutions](#common-git-problems-and-solutions)

## Basic Git Commands

| Command | Description |
|---------|-------------|
| `git init` | Initialize a new Git repository |
| `git clone <repo_url>` | Clone a repository from a remote source |
| `git status` | Show the working directory status |
| `git add <file>` | Add a file to the staging area |
| `git add .` | Add all changes to the staging area |
| `git commit -m "message"` | Commit staged changes with a message |
| `git log` | View commit history |
| `git diff` | Show changes between commits and working directory |
| `git reset <file>` | Unstage a file without removing changes |
| `git rm <file>` | Remove a file from the repository |

## Branching and Merging

| Command | Description |
|---------|-------------|
| `git branch` | List all branches |
| `git branch <branch_name>` | Create a new branch |
| `git checkout <branch_name>` | Switch to a specific branch |
| `git checkout -b <branch_name>` | Create and switch to a new branch |
| `git merge <branch_name>` | Merge a branch into the current branch |
| `git branch -d <branch_name>` | Delete a local branch |

## Remote Repositories

| Command | Description |
|---------|-------------|
| `git remote -v` | Show remote repositories |
| `git remote add origin <url>` | Add a remote repository |
| `git pull origin <branch>` | Fetch and merge changes from remote |
| `git push origin <branch>` | Push changes to a remote repository |
| `git push -u origin <branch>` | Push branch and set upstream tracking |
| `git fetch` | Download changes from remote without merging |

## Undoing Changes

| Command | Description |
|---------|-------------|
| `git checkout -- <file>` | Discard changes in a file |
| `git reset --soft HEAD~1` | Undo last commit, keeping changes staged |
| `git reset --hard HEAD~1` | Undo last commit and discard changes |
| `git revert <commit>` | Revert a specific commit |

## Git Shortcuts

| Shortcut | Description |
|----------|-------------|
| `git commit --amend` | Edit the last commit message |
| `git stash` | Stash uncommitted changes |
| `git stash pop` | Apply the latest stashed changes |
| `git cherry-pick <commit>` | Apply a commit from another branch |
| `git reflog` | Show history of HEAD changes |

## Common Git Problems and Solutions

| Problem | Solution |
|---------|-------------|
| **Forgot to add a file to the last commit** | `git commit --amend --no-edit` after `git add <file>` |
| **Accidentally committed to the wrong branch** | `git reset --soft HEAD~1`, switch branches, and recommit |
| **Merge conflicts occur when pulling changes** | Manually edit the conflicting files, then `git add .` and `git commit -m "Resolve merge conflict"` |
| **Pushed to the wrong branch** | `git push origin --delete <branch>` and push to the correct branch |
| **Need to undo the last pushed commit** | `git revert HEAD` for a safe undo, or `git reset --hard HEAD~1` (if not shared) |
| **Permission denied when pushing to a repo** | Check SSH keys using `ssh -T git@github.com` or update credentials |
| **Git says 'detached HEAD' state** | `git checkout <branch_name>` to switch back to a branch |
| **Need to remove a file from Git history** | `git rm --cached <file>` and then commit and push changes |
