# Git Commands Reference / Référence des commandes Git

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

[Back to README](../README.md)

---

## Table of Contents

- [Setup](#setup)
- [Repository basics](#repository-basics)
- [Staging and commits](#staging-and-commits)
- [Branches](#branches)
- [Remote operations](#remote-operations)
- [Merge and rebase](#merge-and-rebase)
- [Stash](#stash)
- [Tags](#tags)
- [Inspection and history](#inspection-and-history)
- [Undoing changes](#undoing-changes)
- [Advanced operations](#advanced-operations)

---

## Setup

```bash
# Set username globally
git config --global user.name "Your Name"

# Set email globally
git config --global user.email "your@email.com"

# Set default branch name to main
git config --global init.defaultBranch main

# Set default editor
git config --global core.editor "code --wait"

# Enable color output
git config --global color.ui auto

# View all configuration
git config --list

# View a specific setting
git config user.name
```

---

## Repository basics

```bash
# Initialize a new Git repository
git init

# Initialize with a specific branch name
git init -b main

# Clone a repository
git clone https://github.com/user/repo.git

# Clone into a specific folder name
git clone https://github.com/user/repo.git my-folder

# Clone a specific branch
git clone -b develop https://github.com/user/repo.git

# Clone with limited history (faster for large repos)
git clone --depth 1 https://github.com/user/repo.git
```

---

## Staging and commits

```bash
# Check working tree status
git status

# Stage a specific file
git add filename.txt

# Stage a specific folder
git add src/

# Stage all changes
git add .

# Stage parts of a file interactively
git add -p filename.txt

# Remove a file from staging (keep changes)
git reset HEAD filename.txt

# View staged changes
git diff --staged

# View unstaged changes
git diff

# Create a commit
git commit -m "feat: add user authentication"

# Stage tracked files and commit in one command
git commit -am "fix: correct typo in README"

# Amend the last commit (message or content)
git commit --amend

# Amend the last commit message only
git commit --amend -m "new message"

# Create an empty commit (useful for CI triggers)
git commit --allow-empty -m "chore: trigger CI"
```

---

## Branches

```bash
# List local branches
git branch

# List all branches including remote
git branch -a

# List remote branches only
git branch -r

# Create a new branch
git branch feature/my-feature

# Switch to a branch
git checkout feature/my-feature

# Create and switch to a new branch (classic)
git checkout -b feature/my-feature

# Create and switch to a new branch (modern, Git 2.23+)
git switch -c feature/my-feature

# Switch to a branch (modern)
git switch feature/my-feature

# Rename the current branch
git branch -m new-branch-name

# Delete a merged branch
git branch -d feature/my-feature

# Force delete a branch (even if not merged)
git branch -D feature/my-feature

# Set upstream tracking for a branch
git branch -u origin/main

# View branch with last commit info
git branch -v
```

---

## Remote operations

```bash
# List remotes
git remote -v

# Add a remote
git remote add origin git@github.com:user/repo.git

# Add upstream (original repo when working on a fork)
git remote add upstream git@github.com:original-user/repo.git

# Remove a remote
git remote remove origin

# Rename a remote
git remote rename origin old-origin

# Fetch all remotes (no merge)
git fetch --all

# Fetch a specific remote
git fetch origin

# Pull (fetch + merge)
git pull

# Pull with rebase instead of merge
git pull --rebase

# Push to remote
git push

# Push a branch for the first time (set upstream)
git push -u origin feature/my-feature

# Push all branches
git push --all

# Delete a remote branch
git push origin --delete feature/my-feature

# Force push (dangerous, rewrites remote history)
git push --force-with-lease
```

---

## Merge and rebase

```bash
# Merge a branch into current branch (creates a merge commit)
git merge feature/my-feature

# Merge without a merge commit (fast-forward only)
git merge --ff-only feature/my-feature

# Merge and always create a merge commit (even if fast-forward is possible)
git merge --no-ff feature/my-feature

# Abort a merge in progress
git merge --abort

# Rebase current branch onto another
git rebase main

# Interactive rebase (squash, edit, reorder commits)
git rebase -i HEAD~3

# Abort a rebase in progress
git rebase --abort

# Continue a rebase after resolving conflicts
git rebase --continue

# Cherry-pick a specific commit
git cherry-pick abc1234

# Cherry-pick without committing
git cherry-pick -n abc1234
```

---

## Stash

```bash
# Stash current changes
git stash

# Stash with a description
git stash push -m "work in progress on feature X"

# Stash including untracked files
git stash -u

# List all stashes
git stash list

# Apply the most recent stash (and remove it from stash list)
git stash pop

# Apply the most recent stash (keep it in stash list)
git stash apply

# Apply a specific stash
git stash apply stash@{2}

# Drop a specific stash
git stash drop stash@{1}

# Clear all stashes
git stash clear

# Create a branch from a stash
git stash branch feature/from-stash
```

---

## Tags

```bash
# Create a lightweight tag
git tag v1.0.0

# Create an annotated tag (recommended)
git tag -a v1.0.0 -m "Release version 1.0.0"

# Tag a specific commit
git tag -a v1.0.0 abc1234 -m "Release version 1.0.0"

# List all tags
git tag

# List tags with filter
git tag -l "v1.*"

# Show tag details
git show v1.0.0

# Push a specific tag
git push origin v1.0.0

# Push all tags
git push origin --tags

# Delete a local tag
git tag -d v1.0.0

# Delete a remote tag
git push origin --delete v1.0.0
```

---

## Inspection and history

```bash
# View commit history
git log

# Compact one-line log
git log --oneline

# Log with branch graph
git log --oneline --graph --all

# Log for a specific file
git log --follow filename.txt

# Log for a specific author
git log --author="Name"

# Log between dates
git log --after="2024-01-01" --before="2024-12-31"

# Show changes in a specific commit
git show abc1234

# Show who changed each line of a file
git blame filename.txt

# Find commits that introduced a text string
git log -S "search text"

# Find commits where a function changed
git log -G "function_name"

# View the difference between two branches
git diff main..feature/my-feature

# View the difference between two commits
git diff abc1234..def5678

# List files changed in the last commit
git diff --name-only HEAD~1 HEAD

# Count commits in a branch
git rev-list --count main
```

---

## Undoing changes

```bash
# Discard changes in a file (restore to last commit)
git checkout -- filename.txt

# Discard all unstaged changes
git checkout .

# Restore a file (Git 2.23+)
git restore filename.txt

# Unstage a file (keep changes)
git reset HEAD filename.txt

# Unstage a file (Git 2.23+)
git restore --staged filename.txt

# Undo the last commit (keep changes staged)
git reset --soft HEAD~1

# Undo the last commit (keep changes unstaged)
git reset --mixed HEAD~1

# Undo the last commit (discard all changes - dangerous)
git reset --hard HEAD~1

# Revert a commit (safe, creates a new commit)
git revert abc1234

# Revert without auto-committing
git revert -n abc1234

# Revert a merge commit
git revert -m 1 abc1234
```

---

## Advanced operations

```bash
# Clean untracked files and directories
git clean -fd

# Dry run clean (preview what would be deleted)
git clean -fdn

# Bisect to find a bug-introducing commit
git bisect start
git bisect bad          # current commit is bad
git bisect good v1.0.0  # v1.0.0 was good
# ... Git will checkout commits for you to test
git bisect reset        # end bisect session

# Create a patch file
git format-patch HEAD~3

# Apply a patch
git apply my-patch.patch

# Archive the project
git archive --format=zip HEAD > project.zip

# Count objects in the repository
git count-objects -vH

# Compress repository (garbage collection)
git gc

# Check repository integrity
git fsck
```

---

Official documentation : [https://git-scm.com/docs](https://git-scm.com/docs)

[Back to README](../README.md)
