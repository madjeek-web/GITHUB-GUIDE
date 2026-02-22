# GitHub Workflow Guide

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

[Back to README](../README.md)

---

## Table of Contents

- [GitHub Flow](#github-flow)
- [Git Flow](#git-flow)
- [Working with Issues](#working-with-issues)
- [Working with Pull Requests](#working-with-pull-requests)
- [Code Review best practices](#code-review-best-practices)
- [GitHub Projects and Kanban](#github-projects-and-kanban)
- [GitHub Pages](#github-pages)
- [GitHub CLI](#github-cli)

---

## GitHub Flow

GitHub Flow is a simplified branching model designed for teams that deploy frequently. It has six rules.

1. Anything in `main` is always deployable.
2. Create descriptive branches from `main` for any new work.
3. Push to the branch regularly.
4. Open a Pull Request at any time to start discussion.
5. Merge only after review and passing CI.
6. Deploy immediately after merging to `main`.

```
main ─────────────────────────────────────────────────────────> production
         |                               |
         └── feature/login ─────────────┘ (merged via PR)
```

This model is simpler than Git Flow and works well for web applications and services.

Documentation : [https://docs.github.com/en/get-started/using-github/github-flow](https://docs.github.com/en/get-started/using-github/github-flow)

---

## Git Flow

Git Flow is a more structured model for projects with scheduled releases.

```
main ──────────────────────────────── v1.0 ──────────────────> production
  |                                     |
develop ──────────────────────────────────────────────────────>
  |              |          |
  +─ feature/A ──+          |
                  +─ feature/B ─+
                                 +─ release/1.0 ─> main + tag
```

| Branch | Created from | Merges into | Purpose |
|---|---|---|---|
| `main` | Initial commit | - | Stable production code |
| `develop` | `main` | `main` via release | Integration branch |
| `feature/*` | `develop` | `develop` | New features |
| `release/*` | `develop` | `main` + `develop` | Release preparation |
| `hotfix/*` | `main` | `main` + `develop` | Urgent production fixes |

### When to use Git Flow

Git Flow suits projects that have clear versioned releases, a QA process, or multiple versions in production simultaneously. For simpler projects or teams that deploy continuously, GitHub Flow or Trunk Based Development are often better choices.

Trunk Based Development : [https://trunkbaseddevelopment.com/](https://trunkbaseddevelopment.com/)

---

## Working with Issues

Issues are the primary way to track work, bugs, and discussions in a GitHub project.

### Creating a good issue

A good issue includes a clear title, context, and enough detail for someone else to understand and act on it without needing to ask questions.

For a bug report, include the steps to reproduce, the expected behavior, the actual behavior, and the environment (OS, version, etc.).

For a feature request, explain the problem being solved, not just the solution. This leaves room for better solutions to emerge.

### Using labels

Labels help organize and filter issues. A typical label setup :

| Label | Color | Meaning |
|---|---|---|
| `bug` | Red | Something is broken |
| `enhancement` | Blue | New feature request |
| `documentation` | Teal | Docs improvement |
| `good first issue` | Green | Good for newcomers |
| `help wanted` | Yellow | External help welcome |
| `question` | Pink | Needs clarification |
| `wontfix` | Gray | Will not be addressed |
| `duplicate` | Gray | Already reported |
| `in progress` | Orange | Currently being worked on |

### Milestones

Milestones group issues and pull requests around a goal or a release. They show progress toward a target. Create milestones in Issues > Milestones.

### Closing issues via commits

Reference issues in commit messages or PR descriptions to close them automatically when merged :

```
Closes #42
Fixes #42
Resolves #42
```

Multiple issues can be closed : `Closes #42, Closes #43`.

---

## Working with Pull Requests

### Opening a Pull Request

A PR is opened when you want to propose merging one branch into another. On GitHub, go to your branch, then click "Compare and pull request".

A good PR :

- Has a clear title describing the change, not the implementation
- Has a description that explains what was changed and why
- References any related issues
- Is as small and focused as possible
- Does not mix unrelated changes
- Includes screenshots or examples for UI changes

### Draft Pull Requests

Use draft PRs when your work is not yet ready for review but you want to share progress, run CI, or get early feedback. Click the dropdown arrow next to "Create pull request" and select "Create draft pull request". Mark it as ready when done.

### Reviewers and CODEOWNERS

Add reviewers to your PR to request their review. For projects that want to enforce review by specific people, a `CODEOWNERS` file can be placed in `.github/CODEOWNERS` :

```
# All files require review from madjeek-web
*   @madjeek-web

# Files in docs/ require review from the docs team
docs/   @madjeek-web
```

Documentation : [https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners)

### Branch protection rules

Branch protection rules prevent direct pushes to important branches and require PR reviews before merging. Configure them in Settings > Branches > Branch protection rules.

Common settings :

- Require a pull request before merging
- Require approvals (at least 1)
- Dismiss stale reviews when new commits are pushed
- Require status checks to pass before merging
- Require conversation resolution before merging

---

## Code Review best practices

### As a reviewer

- Review the intent, not just the implementation
- Ask questions instead of making demands
- Be specific about what should change and why
- Approve when satisfied, even if minor nits remain
- Use "Request changes" only when the PR cannot be merged as-is
- Respond within a reasonable time

### As the author

- Keep your PRs focused and small
- Explain your choices in comments if they are not obvious
- Respond to all review comments, even just to acknowledge
- Do not take feedback personally
- Update the PR promptly after feedback

### Review comment prefixes (common convention)

| Prefix | Meaning |
|---|---|
| `nit:` | Minor style suggestion, optional |
| `q:` | Genuine question, not a required change |
| `suggestion:` | Possible improvement, author's choice |
| `blocker:` | Must be fixed before merging |

---

## GitHub Projects and Kanban

GitHub Projects allows you to organize issues and PRs on a Kanban board or as a table.

### Creating a project

1. Go to your profile or organization page.
2. Click the "Projects" tab.
3. Click "New project".
4. Choose "Board" for Kanban view or "Table" for spreadsheet view.

### Typical Kanban columns

| Column | Meaning |
|---|---|
| Backlog | Ideas and future work |
| Todo | Ready to start |
| In Progress | Currently being worked on |
| In Review | PR opened, awaiting review |
| Done | Merged or completed |

Documentation : [https://docs.github.com/en/issues/planning-and-tracking-with-projects](https://docs.github.com/en/issues/planning-and-tracking-with-projects)

---

## GitHub Pages

GitHub Pages allows you to publish a static website directly from a repository for free.

### Enabling GitHub Pages

1. Go to repository Settings > Pages.
2. Under "Source", select the branch to publish from (usually `main` or `gh-pages`).
3. Select the folder (`/` root or `/docs`).
4. Save. GitHub will build and publish your site.

Your site will be available at `https://username.github.io/repository-name/`.

### Using Jekyll (optional)

GitHub Pages supports Jekyll, a static site generator. Add a `_config.yml` at the root to configure it. Jekyll supports themes, layouts, and Markdown natively.

Documentation : [https://docs.github.com/en/pages](https://docs.github.com/en/pages)

---

## GitHub CLI

The GitHub CLI (`gh`) allows you to interact with GitHub directly from the terminal, without opening a browser.

Installation : [https://cli.github.com/](https://cli.github.com/)

### Common commands

```bash
# Authenticate
gh auth login

# Clone a repository
gh repo clone user/repo

# Create a new repository
gh repo create my-repo --public

# View repository info
gh repo view

# Create an issue
gh issue create --title "Bug: login fails" --body "Description..."

# List issues
gh issue list

# Create a Pull Request
gh pr create --title "feat: add user auth" --body "Description..."

# List PRs
gh pr list

# Check PR status
gh pr status

# Merge a PR
gh pr merge 42 --merge

# View CI runs
gh run list

# Watch a CI run
gh run watch

# Create a release
gh release create v1.0.0 --title "Version 1.0.0" --notes "Release notes..."
```

Documentation : [https://cli.github.com/manual/](https://cli.github.com/manual/)

---

[Back to README](../README.md)
