# Glossary / Glossaire Git and GitHub

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

[Back to README](../README.md)

---

This glossary covers the key terms you will encounter when working with Git and GitHub. Each entry includes a brief explanation in English and French.

---

## A

### Annotated tag / Tag annoté

A tag that stores metadata : the tagger's name, email, date, and a message. Created with `git tag -a`. Recommended over lightweight tags for marking releases.

FR : Un tag qui stocke des métadonnées : le nom du créateur, son e-mail, la date et un message. Créé avec `git tag -a`. Recommandé pour marquer les versions.

### Authentication / Authentification

The process of proving your identity to GitHub. Can be done via HTTPS with a personal access token, or via SSH with a key pair. SSH is recommended for daily use.

FR : Le processus qui prouve votre identité à GitHub. Peut se faire via HTTPS avec un token, ou via SSH avec une paire de clés. SSH est recommandé pour un usage quotidien.

---

## B

### Base branch / Branche de base

The branch into which changes will be merged in a Pull Request. Often `main` or `develop`.

FR : La branche dans laquelle les changements seront fusionnés lors d'une Pull Request. Souvent `main` ou `develop`.

### Bisect / Bisection

A Git command (`git bisect`) that uses binary search to find the commit that introduced a bug. You mark a known-bad commit and a known-good commit, and Git guides you through the history to pinpoint the offending commit.

FR : Une commande Git (`git bisect`) qui utilise la recherche binaire pour trouver le commit qui a introduit un bug. Vous marquez un commit mauvais connu et un bon connu, et Git vous guide dans l'historique pour identifier le commit responsable.

### Branch / Branche

A lightweight movable pointer to a commit. Branches let you work on different features or fixes in isolation without affecting the main codebase. The default branch is usually named `main`.

FR : Un pointeur léger et mobile vers un commit. Les branches permettent de travailler sur différentes fonctionnalités ou corrections en isolation, sans affecter le code principal. La branche par défaut s'appelle généralement `main`.

---

## C

### Cherry-pick

The process of applying a specific commit from one branch to another without merging the entire branch. Useful for applying hotfixes or backporting specific changes.

FR : Le processus d'application d'un commit spécifique d'une branche vers une autre, sans fusionner toute la branche. Utile pour appliquer des correctifs urgents ou reporter des changements spécifiques.

### CI/CD (Continuous Integration / Continuous Deployment)

A development practice where code changes are automatically built, tested, and sometimes deployed. CI catches integration problems early. CD automates the release process. GitHub Actions is the tool used on GitHub.

FR : Une pratique de développement où les changements de code sont automatiquement construits, testés et parfois déployés. La CI détecte les problèmes d'intégration tôt. La CD automatise le processus de publication. GitHub Actions est l'outil utilisé sur GitHub.

### Clone

The operation of downloading a complete copy of a remote repository to your local machine, including all commits and branches. Done with `git clone`.

FR : L'opération qui télécharge une copie complète d'un dépôt distant sur votre machine locale, y compris tous les commits et branches. Effectué avec `git clone`.

### Commit

A snapshot of the repository at a specific point in time. Each commit records what changed, who changed it, when, and why (via the message). Commits form a chain that represents the project history.

FR : Un instantané du dépôt à un moment précis. Chaque commit enregistre ce qui a changé, qui l'a changé, quand et pourquoi (via le message). Les commits forment une chaîne qui représente l'historique du projet.

### Conflict / Conflit

A situation where Git cannot automatically merge changes because two branches modified the same part of a file in different ways. Conflicts must be resolved manually before the merge can be completed.

FR : Une situation où Git ne peut pas fusionner automatiquement des changements car deux branches ont modifié le même endroit d'un fichier de façon différente. Les conflits doivent être résolus manuellement avant que la fusion puisse être finalisée.

### CODEOWNERS

A special file placed in `.github/CODEOWNERS` that defines which people or teams are responsible for reviewing specific files or directories. GitHub automatically requests reviews from code owners when PRs affect their files.

FR : Un fichier spécial placé dans `.github/CODEOWNERS` qui définit quelles personnes ou équipes sont responsables de la relecture de fichiers ou dossiers spécifiques. GitHub demande automatiquement leurs avis lors des PRs qui affectent leurs fichiers.

---

## D

### Default branch / Branche par défaut

The branch shown by default when someone visits the repository, and the target branch for new pull requests. Configured in repository Settings. Historically named `master`, now commonly `main`.

FR : La branche affichée par défaut quand quelqu'un visite le dépôt, et la branche cible pour les nouvelles pull requests. Configuré dans les paramètres du dépôt. Historiquement nommée `master`, maintenant souvent `main`.

### Dependabot

A GitHub tool that automatically checks your project's dependencies for known vulnerabilities and opens pull requests to update them.

FR : Un outil GitHub qui vérifie automatiquement les dépendances de votre projet pour détecter des vulnérabilités connues et ouvre des pull requests pour les mettre à jour.

---

## F

### Fast-forward

A type of merge where Git simply moves the base branch pointer forward to the tip of the merged branch, because there are no diverging commits. No merge commit is created.

FR : Un type de fusion où Git déplace simplement le pointeur de la branche de base vers la pointe de la branche fusionnée, car il n'y a pas de commits divergents. Aucun commit de fusion n'est créé.

### Fetch

The operation of downloading objects and references from a remote repository without merging them into your local branches. Allows you to see what changed remotely before deciding to integrate it.

FR : L'opération qui télécharge les objets et références d'un dépôt distant sans les fusionner dans vos branches locales. Permet de voir ce qui a changé à distance avant de décider de l'intégrer.

### Fork

A server-side copy of a repository under a different user's or organization's account. Forking is the standard way to contribute to projects you do not have write access to. Your fork is fully independent.

FR : Une copie côté serveur d'un dépôt sous le compte d'un autre utilisateur ou d'une organisation. Le fork est la façon standard de contribuer à des projets auxquels vous n'avez pas accès en écriture. Votre fork est totalement indépendant.

---

## G

### Git

A free and open-source distributed version control system created by Linus Torvalds in 2005 for Linux kernel development. Git is installed locally and works independently of any online service.

FR : Un système de contrôle de version distribué, libre et gratuit, créé par Linus Torvalds en 2005 pour le développement du noyau Linux. Git est installé localement et fonctionne indépendamment de tout service en ligne.

### Git Flow

A branching model created by Vincent Driessen that defines a strict set of branch types and merge rules. Suited for projects with scheduled releases. See [nvie.com/posts/a-successful-git-branching-model](https://nvie.com/posts/a-successful-git-branching-model/).

FR : Un modèle de branches créé par Vincent Driessen qui définit un ensemble strict de types de branches et de règles de fusion. Adapté aux projets avec des versions planifiées.

### .gitignore

A text file that tells Git which files and folders to ignore and not track. Placed at the root of the repository. Patterns use glob syntax. Lines starting with `#` are comments.

FR : Un fichier texte qui indique à Git quels fichiers et dossiers ignorer et ne pas suivre. Placé à la racine du dépôt. Les patterns utilisent la syntaxe glob. Les lignes commençant par `#` sont des commentaires.

### GitHub

A web-based platform that hosts Git repositories and provides collaboration features : Issues, Pull Requests, GitHub Actions, GitHub Pages, and more. Owned by Microsoft since 2018.

FR : Une plateforme web qui héberge des dépôts Git et fournit des fonctionnalités de collaboration : Issues, Pull Requests, GitHub Actions, GitHub Pages, et plus encore. Appartient à Microsoft depuis 2018.

### GitHub Actions

GitHub's built-in CI/CD and automation platform. Workflows are defined in YAML files in `.github/workflows/`. They are triggered by events like push, pull request, or schedule.

FR : La plateforme CI/CD et d'automatisation intégrée à GitHub. Les workflows sont définis en YAML dans `.github/workflows/`. Ils sont déclenchés par des événements comme un push, une pull request ou un planning.

---

## H

### HEAD

A special pointer that refers to the currently checked-out commit or branch. When you are on a branch, HEAD points to that branch. When you check out a specific commit directly, Git enters "detached HEAD" state.

FR : Un pointeur spécial qui référence le commit ou la branche actuellement extrait. Quand vous êtes sur une branche, HEAD pointe vers cette branche. Quand vous extrayez directement un commit spécifique, Git entre en état "HEAD détaché".

### Hotfix

An urgent fix applied directly to the production branch (`main`) without going through the normal development branch. In Git Flow, hotfix branches are created from `main` and merged back into both `main` and `develop`.

FR : Un correctif urgent appliqué directement sur la branche de production (`main`) sans passer par la branche de développement normale. Dans Git Flow, les branches hotfix sont créées depuis `main` et fusionnées dans `main` et `develop`.

---

## I

### Index

Another name for the staging area. The index is a file Git maintains that tracks what will be included in the next commit.

FR : Un autre nom pour la zone de staging. L'index est un fichier que Git maintient et qui suit ce qui sera inclus dans le prochain commit.

### Issue

A GitHub feature for tracking tasks, bugs, feature requests, and discussions. Issues can be labeled, assigned, linked to milestones, and closed by commits.

FR : Une fonctionnalité GitHub pour suivre les tâches, bugs, demandes de fonctionnalités et discussions. Les issues peuvent être labelisées, assignées, liées à des milestones et fermées par des commits.

---

## L

### Label

A tag applied to an issue or pull request to categorize it. Labels are customizable per repository and help with filtering and prioritization.

FR : Un tag appliqué à une issue ou une pull request pour la catégoriser. Les labels sont personnalisables par dépôt et aident au filtrage et à la priorisation.

### License / Licence

A legal document that specifies how the software can be used, modified, and distributed. Common choices include MIT (very permissive), Apache 2.0, and GPL (copyleft). A project without a license is not open source by default.

FR : Un document légal qui spécifie comment le logiciel peut être utilisé, modifié et distribué. Les choix courants incluent MIT (très permissive), Apache 2.0 et GPL (copyleft). Un projet sans licence n'est pas open source par défaut.

---

## M

### Maintainer

A person who manages and is responsible for the direction of an open source project. They review and merge contributions, handle releases, and make architectural decisions.

FR : Une personne qui gère et est responsable de la direction d'un projet open source. Elle relit et fusionne les contributions, gère les versions et prend les décisions architecturales.

### Merge

The process of integrating changes from one branch into another. Git can merge automatically if there are no conflicts. A merge commit records the integration of two branches.

FR : Le processus d'intégration des changements d'une branche dans une autre. Git peut fusionner automatiquement en l'absence de conflits. Un commit de fusion enregistre l'intégration de deux branches.

### Milestone

A GitHub feature for grouping issues and pull requests under a goal with a target date. Milestones show progress toward a release or project phase.

FR : Une fonctionnalité GitHub pour regrouper des issues et des pull requests autour d'un objectif avec une date cible. Les milestones montrent la progression vers une version ou une phase de projet.

---

## O

### Origin

The conventional name given to the primary remote repository. When you clone a repository, Git automatically names the remote `origin`. When working with a fork, `origin` is your fork and `upstream` is the original.

FR : Le nom conventionnel donné au dépôt distant principal. Quand vous clonez un dépôt, Git nomme automatiquement le remote `origin`. Quand on travaille avec un fork, `origin` est votre fork et `upstream` est l'original.

---

## P

### Pull

The operation of fetching commits from a remote repository and merging them into the current local branch. `git pull` is equivalent to `git fetch` followed by `git merge`.

FR : L'opération qui récupère les commits d'un dépôt distant et les fusionne dans la branche locale courante. `git pull` est équivalent à `git fetch` suivi de `git merge`.

### Pull Request (PR)

A GitHub feature for proposing that changes from one branch be merged into another. PRs enable code review, discussion, and CI checks before code is integrated.

FR : Une fonctionnalité GitHub pour proposer de fusionner les changements d'une branche dans une autre. Les PRs permettent la revue de code, les discussions et les vérifications CI avant l'intégration du code.

### Push

The operation of sending local commits to a remote repository. `git push` requires write access to the remote.

FR : L'opération qui envoie les commits locaux vers un dépôt distant. `git push` nécessite un accès en écriture sur le dépôt distant.

---

## R

### Rebase

A Git operation that moves or replays a series of commits onto a new base commit. Rebase rewrites commit history and produces a cleaner, linear history compared to merge. Should not be used on shared branches.

FR : Une opération Git qui déplace ou rejoue une série de commits sur un nouveau commit de base. Le rebase réécrit l'historique des commits et produit un historique plus propre et linéaire que le merge. Ne doit pas être utilisé sur des branches partagées.

### Release

A published version of a project on GitHub. A release is tied to a Git tag and can include release notes and attached files (binaries, archives, etc.).

FR : Une version publiée d'un projet sur GitHub. Une release est liée à un tag Git et peut inclure des notes de version et des fichiers joints (binaires, archives, etc.).

### Remote

A version of the repository hosted on a server (like GitHub). You can have multiple remotes. The main one is conventionally named `origin`.

FR : Une version du dépôt hébergée sur un serveur (comme GitHub). Vous pouvez avoir plusieurs remotes. Le principal s'appelle conventionnellement `origin`.

### Repository (repo) / Dépôt

The data structure where Git stores all versions of your project's files and their history. A repository contains all commits, branches, tags, and configuration.

FR : La structure de données où Git stocke toutes les versions des fichiers de votre projet et leur historique. Un dépôt contient tous les commits, branches, tags et la configuration.

### Revert

A Git command that creates a new commit that undoes the changes of a previous commit. Unlike `reset`, it does not rewrite history, making it safe to use on shared branches.

FR : Une commande Git qui crée un nouveau commit qui annule les changements d'un commit précédent. Contrairement à `reset`, elle ne réécrit pas l'historique, ce qui la rend sûre à utiliser sur des branches partagées.

---

## S

### Semantic Versioning (SemVer)

A versioning convention : MAJOR.MINOR.PATCH. MAJOR is incremented for breaking changes. MINOR for new backward-compatible features. PATCH for backward-compatible bug fixes. See [semver.org](https://semver.org/).

FR : Une convention de versionnage : MAJEUR.MINEUR.PATCH. MAJEUR est incrémenté pour les changements incompatibles. MINEUR pour les nouvelles fonctionnalités compatibles. PATCH pour les correctifs compatibles.

### Squash

Combining multiple commits into a single commit. Often used before merging a feature branch to simplify the history. Can be done interactively with `git rebase -i`.

FR : La combinaison de plusieurs commits en un seul. Souvent utilisé avant de fusionner une branche de fonctionnalité pour simplifier l'historique. Peut être fait de façon interactive avec `git rebase -i`.

### Staging area / Zone de staging

The intermediate area between the working directory and the repository. Files must be staged (added to the staging area) before they can be committed. Also called the index.

FR : La zone intermédiaire entre le répertoire de travail et le dépôt. Les fichiers doivent être mis en staging (ajoutés à la zone de staging) avant de pouvoir être commités. Aussi appelée l'index.

### Stash

A Git feature for temporarily saving changes that are not ready to commit. The stash is a stack : you can push multiple stashes and pop them in reverse order.

FR : Une fonctionnalité Git pour sauvegarder temporairement des changements qui ne sont pas prêts à être commités. Le stash est une pile : vous pouvez empiler plusieurs stashes et les dépiler dans l'ordre inverse.

---

## T

### Tag

A named reference to a specific commit. Tags are typically used to mark release points (v1.0.0, v2.3.1). Unlike branches, tags do not move as new commits are made.

FR : Une référence nommée vers un commit spécifique. Les tags sont typiquement utilisés pour marquer des points de version (v1.0.0, v2.3.1). Contrairement aux branches, les tags ne bougent pas quand de nouveaux commits sont créés.

### Trunk Based Development

A source control branching model where developers collaborate on code in a single branch called the trunk (or `main`). Short-lived feature branches are optional but must be short-lived. See [trunkbaseddevelopment.com](https://trunkbaseddevelopment.com/).

FR : Un modèle de branches où les développeurs collaborent sur une branche unique appelée le tronc (ou `main`). Des branches de fonctionnalités de courte durée sont optionnelles. Voir [trunkbaseddevelopment.com](https://trunkbaseddevelopment.com/).

---

## U

### Upstream

1. The original repository when you are working from a fork. You fetch updates from upstream to keep your fork current.
2. In the context of `git push -u`, upstream refers to the remote branch that a local branch tracks.

FR : 1. Le dépôt original quand vous travaillez depuis un fork. Vous récupérez les mises à jour depuis upstream pour maintenir votre fork à jour. 2. Dans le contexte de `git push -u`, upstream désigne la branche distante que la branche locale suit.

---

## W

### Working directory / Répertoire de travail

The local folder on your computer where you edit files. Changes in the working directory are not tracked by Git until you stage them with `git add`.

FR : Le dossier local sur votre ordinateur où vous éditez les fichiers. Les changements dans le répertoire de travail ne sont pas suivis par Git tant que vous ne les mettez pas en staging avec `git add`.

### Workflow

1. In general : the process a team follows to develop and ship software.
2. In GitHub Actions : a YAML file in `.github/workflows/` that defines an automation.

FR : 1. En général : le processus qu'une équipe suit pour développer et livrer des logiciels. 2. Dans GitHub Actions : un fichier YAML dans `.github/workflows/` qui définit une automatisation.

---

[Back to README](../README.md)
