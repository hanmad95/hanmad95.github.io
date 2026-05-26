---
title: Git Tips and Tricks
date: 2025-03-05 09:45:00 +0100
categories: [Development Tools, Git]
tags: [git, version-control, workflow, tips]
---

# Git Tips and Tricks 🔧

Git is an essential tool for any developer. Here are some tips to boost your productivity and improve your workflow.

## Useful Git Configurations

```bash
# Set your identity
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Set default branch name to 'main'
git config --global init.defaultBranch main

# Enable colors in git output
git config --global color.ui true

# Set your favorite editor
git config --global core.editor "vim"
```

## Viewing Commit History

```bash
# View compact log
git log --oneline

# See changes in each commit
git log -p

# View log with graph
git log --graph --oneline --all

# Find commits by author
git log --author="John"

# Find commits matching a message
git log --grep="bug fix"
```

## Staging and Committing

```bash
# Stage specific files
git add file1.js file2.js

# Stage all changes
git add .

# Stage parts of a file interactively
git add -p

# Unstage files
git reset HEAD file.js

# Discard changes in working directory
git checkout -- file.js
```

## Branching Strategies

```bash
# Create and switch to new branch
git checkout -b feature/user-auth

# List all branches
git branch -a

# Delete branch
git branch -d feature/user-auth

# Rename current branch
git branch -m old-name new-name
```

## Undoing Changes

```bash
# Undo last commit (keep changes)
git reset --soft HEAD~1

# Undo last commit (discard changes)
git reset --hard HEAD~1

# Amend last commit
git commit --amend -m "New message"

# View undo history
git reflog
```

## Stashing Work

```bash
# Save changes without committing
git stash

# Apply most recent stash
git stash pop

# Apply specific stash
git stash apply stash@{2}

# List all stashes
git stash list

# Delete a stash
git stash drop stash@{0}
```

## Finding Bugs

```bash
# Find which commit introduced a bug
git bisect start
git bisect bad HEAD
git bisect good v1.0

# Find who changed a specific line
git blame file.js

# Search for deleted content
git log -p -S "search-term"
```

## Merging and Rebasing

```bash
# Merge branch into current branch
git merge feature/new-feature

# Rebase current branch on main
git rebase main

# Interactive rebase (squash/reorder commits)
git rebase -i HEAD~3
```

## Advanced Tip: Git Aliases

```bash
# Create custom commands
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.unstage 'reset HEAD --'
git config --global alias.last 'log -1 HEAD'
git config --global alias.visual 'log --graph --oneline --all'
```

Now you can use `git visual` instead of the long log command!

## Pro Tips

1. **Commit frequently**: Small, logical commits are easier to understand and revert
2. **Write clear commit messages**: "Fix bug" vs "Fix null pointer in user validation"
3. **Pull before push**: Always sync with remote before pushing
4. **Use .gitignore**: Keep unnecessary files out of your repo
5. **Review before committing**: `git diff` before `git add`

Master these commands and you'll become a Git ninja! 🥋
