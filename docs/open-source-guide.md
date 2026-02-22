# Open Source Contribution Guide / Guide de Contribution Open Source

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

[Back to README](../README.md)

---

## Table of Contents

- [What is open source](#what-is-open-source)
- [Why contribute](#why-contribute)
- [Finding projects to contribute to](#finding-projects-to-contribute-to)
- [Understanding a project before contributing](#understanding-a-project-before-contributing)
- [Full contribution workflow](#full-contribution-workflow)
- [Types of contributions](#types-of-contributions)
- [Communication etiquette](#communication-etiquette)
- [Resources](#resources)

---

## What is open source

Open source software is software whose source code is made publicly available under a license that allows anyone to read, use, modify, and distribute it. The term comes from the practice of opening the source code so anyone can inspect and improve it.

The open source model has produced some of the most important software in the world : Linux, Git, Python, Firefox, React, Kubernetes, PostgreSQL, and many others.

Open source is not just about code. Documentation, design, translation, and community management are all forms of open source contribution.

The Open Source Initiative maintains the official definition : [https://opensource.org/osd](https://opensource.org/osd)

---

## Why contribute

Contributing to open source provides several concrete benefits :

You build real-world experience working on code used by actual users. You learn to read and navigate large, unfamiliar codebases. You develop collaboration skills by working with distributed teams. You build a portfolio that employers can verify, since your contributions are public. You give back to the tools and libraries you use every day. You may be invited to become a regular contributor or maintainer over time.

For a first-year developer, a few quality open source contributions can stand out significantly on a resume compared to personal projects that are never seen by others.

---

## Finding projects to contribute to

Start with tools you already use. If you use a library, framework, or CLI tool daily, you are in a good position to notice bugs or missing documentation.

| Resource | URL | What it is |
|---|---|---|
| GitHub Explore | [github.com/explore](https://github.com/explore) | Discover trending projects |
| Good First Issues | [goodfirstissue.dev](https://goodfirstissue.dev/) | Curated beginner-friendly issues |
| Up For Grabs | [up-for-grabs.net](https://up-for-grabs.net/) | Projects looking for contributors |
| First Timers Only | [firsttimersonly.com](https://www.firsttimersonly.com/) | Issues reserved for first-time contributors |
| CodeTriage | [codetriage.com](https://www.codetriage.com/) | Daily open source issues by email |
| Open Source Guide | [opensource.guide](https://opensource.guide/) | Comprehensive guide from GitHub |

### What to look for in a project

Before choosing a project, check a few signals :

- Is there recent activity ? A project with no commits in 2 years may be abandoned.
- Are issues being responded to ? Look at open issues and how long they sit without response.
- Is there a CONTRIBUTING.md ? Projects that have thought about onboarding contributors are easier to work with.
- Are PRs being reviewed and merged ? Check the merged PR list.
- Is the communication respectful ? Read some issue threads to get a sense of the community tone.

---

## Understanding a project before contributing

Before writing a single line of code, spend time understanding the project.

Read the README fully. It tells you what the project does, how to install it, and often how to run it locally.

Read the CONTRIBUTING.md if it exists. It explains the exact process the project expects : branch naming, commit format, test requirements, how to run the test suite locally.

Look at recent merged PRs. They show what good contributions look like in this specific project, what gets approved, and what gets rejected.

Look at the issues labeled `good first issue` or `help wanted`. These are specifically marked as accessible for new contributors.

Set up the project locally and run it before changing anything. Understand how to run the tests. A contribution that breaks tests will not be merged.

---

## Full contribution workflow

### Step 1 : Fork the repository

Go to the project page on GitHub and click "Fork" in the top right corner. This creates a personal copy of the repository under your account.

### Step 2 : Clone your fork

```bash
git clone git@github.com:your-username/project-name.git
cd project-name
```

### Step 3 : Add the upstream remote

This connects your local clone to the original repository so you can keep your fork up to date.

```bash
git remote add upstream git@github.com:original-author/project-name.git
```

Verify your remotes :

```bash
git remote -v
# origin    git@github.com:your-username/project-name.git (fetch)
# origin    git@github.com:your-username/project-name.git (push)
# upstream  git@github.com:original-author/project-name.git (fetch)
# upstream  git@github.com:original-author/project-name.git (push)
```

### Step 4 : Create a branch

Never work directly on `main`. Create a dedicated branch for each contribution.

```bash
git checkout -b fix/correct-typo-in-readme
```

Use a descriptive name. `fix/correct-typo-in-readme` is better than `my-fix` or `branch1`.

### Step 5 : Make your changes

Write your code or documentation. Follow the project's existing style, naming conventions, and structure. If the project has a linter or formatter configured, run it.

### Step 6 : Test your changes

Run the project's test suite before committing :

```bash
# Node.js example
npm test

# Python example
pytest

# PHP example
vendor/bin/phpunit
```

If you are fixing a bug, add a test that reproduces the bug first, then fix the bug and verify the test passes.

### Step 7 : Commit your changes

```bash
git add .
git commit -m "fix: correct typo in installation section of README"
```

Follow the commit convention used by the project. Many projects use Conventional Commits : [https://www.conventionalcommits.org/](https://www.conventionalcommits.org/en/v1.0.0/)

### Step 8 : Keep your branch up to date

Before pushing, sync with the latest changes from the original repository :

```bash
git fetch upstream
git rebase upstream/main
```

Resolve any conflicts that arise, then continue :

```bash
git rebase --continue
```

### Step 9 : Push your branch

```bash
git push origin fix/correct-typo-in-readme
```

If you rebased after already pushing, you may need to force push (only do this on your own fork, never on shared branches) :

```bash
git push origin fix/correct-typo-in-readme --force-with-lease
```

### Step 10 : Open the Pull Request

Go to your fork on GitHub. You will see a banner suggesting to compare and open a PR. Click it. Set the base repository to the original project and the base branch to `main` (or `develop`, check the project's convention).

Write a clear PR description :

- What does this PR do ?
- Why is it needed ?
- How was it tested ?
- Reference the related issue : `Closes #42`

### Step 11 : Respond to review

The maintainer will review your PR. They may request changes. This is normal and not a rejection. Update your branch, push again, and the PR will update automatically.

Stay patient. Maintainers are often volunteers and may take days or weeks to review. Following up politely after a week or two is fine.

### Step 12 : After merge

Once your PR is merged, clean up :

```bash
# Update your local main
git checkout main
git pull upstream main

# Delete your feature branch locally
git branch -d fix/correct-typo-in-readme

# Delete the remote branch
git push origin --delete fix/correct-typo-in-readme
```

---

## Types of contributions

Open source contributions are not limited to code. All of these are valuable :

| Type | Examples |
|---|---|
| Bug fixes | Finding and fixing errors in code |
| New features | Implementing functionality from the roadmap |
| Documentation | Improving README, writing tutorials, fixing examples |
| Translation | Translating docs or interface strings |
| Tests | Adding missing tests, improving coverage |
| Design | Improving UI, creating icons, improving UX |
| Code review | Reviewing other people's pull requests |
| Issue triage | Labeling, reproducing, and organizing issues |
| Community | Answering questions in issues or discussions |

For a beginner, documentation fixes and issue triage are excellent ways to start. They require less technical knowledge and are very valuable to projects that often have poor documentation.

---

## Communication etiquette

Open source communication is mostly asynchronous and text-based. Misunderstandings are common. A few principles help.

Be specific. Vague comments like "this is wrong" are not useful. Explain what the problem is and why.

Be kind. Assume good intent. The person you are communicating with is likely a volunteer spending their free time on something they care about.

Be patient. Response times vary. Maintainers have jobs, families, and lives outside open source.

Be open to feedback. Your first instinct about the right solution may not be correct. Treat feedback as an opportunity to learn.

Avoid entitlement. Nobody owes you a review, a merge, or a specific feature. Open source maintainers choose what to include in their project.

When in doubt, refer to the project's code of conduct.

---

## Resources

| Resource | URL |
|---|---|
| How to Contribute to Open Source | [opensource.guide/how-to-contribute](https://opensource.guide/how-to-contribute/) |
| Finding Ways to Contribute | [opensource.guide/finding-a-project](https://opensource.guide/finding-a-project/) |
| Being a Good Open Source Citizen | [opensource.guide/code-of-conduct](https://opensource.guide/code-of-conduct/) |
| GitHub Docs : Contributing to a project | [docs.github.com](https://docs.github.com/en/get-started/exploring-projects-on-github/contributing-to-a-project) |
| All Contributors Spec | [allcontributors.org](https://allcontributors.org/) |
| Hacktoberfest | [hacktoberfest.com](https://hacktoberfest.com/) |

---

[Back to README](../README.md)
