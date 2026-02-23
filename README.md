[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub stars](https://img.shields.io/github/stars/madjeek-web/GITHUB-GUIDE?style=social)](https://github.com/madjeek-web/GITHUB-GUIDE/stargazers)
[![GitHub last commit](https://img.shields.io/github/last-commit/madjeek-web/GITHUB-GUIDE)](https://github.com/madjeek-web/GITHUB-GUIDE/commits/main)
[![Maintained](https://img.shields.io/badge/Maintained-yes-green.svg)](https://github.com/madjeek-web/GITHUB-GUIDE)
[![GitHub forks](https://img.shields.io/github/forks/madjeek-web/GITHUB-GUIDE?style=social)](https://github.com/madjeek-web/GITHUB-GUIDE/network/members)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

---

# GITHUB-GUIDE

> Guide complet Git et GitHub pour débutants et développeurs juniors.
> Complete Git and GitHub guide for beginners and junior developers.

---

**Lire en français** : [Section française](#-version-française)  
**Read in English** : [English section](#-english-version)

---

## Table des matières / Table of Contents

### Français

- [A propos de ce guide](#a-propos-de-ce-guide)
- [Prérequis](#prérequis)
- [Comprendre Git et GitHub](#comprendre-git-et-github)
- [Installation et configuration](#installation-et-configuration)
- [Structure d'un dépôt professionnel](#structure-dun-dépôt-professionnel)
- [Créer sa structure depuis l'interface web GitHub](#créer-sa-structure-depuis-linterface-web-github)
- [Créer sa structure depuis la ligne de commande](#créer-sa-structure-depuis-la-ligne-de-commande)
- [Commandes Git essentielles](#commandes-git-essentielles)
- [Branches et workflow](#branches-et-workflow)
- [Messages de commit](#messages-de-commit)
- [GitHub Actions et CI/CD](#github-actions-et-cicd)
- [Contribuer à un projet open source](#contribuer-à-un-projet-open-source)
- [Fichiers importants d'un dépôt](#fichiers-importants-dun-dépôt)
- [Badges GitHub](#badges-github)
- [Ressources et liens](#ressources-et-liens)
- [Lexique Git et GitHub](#lexique-git-et-github)
- [FAQ Français](#faq-français)

### English

- [About this guide](#about-this-guide)
- [Prerequisites](#prerequisites)
- [Understanding Git and GitHub](#understanding-git-and-github)
- [Installation and configuration](#installation-and-configuration)
- [Professional repository structure](#professional-repository-structure)
- [Creating structure from the GitHub web interface](#creating-structure-from-the-github-web-interface)
- [Creating structure from the command line](#creating-structure-from-the-command-line)
- [Essential Git commands](#essential-git-commands)
- [Branches and workflow](#branches-and-workflow-1)
- [Commit messages](#commit-messages)
- [GitHub Actions and CI/CD](#github-actions-and-cicd-1)
- [Contributing to open source](#contributing-to-open-source)
- [Important repository files](#important-repository-files)
- [GitHub Badges](#github-badges)
- [Resources and links](#resources-and-links)
- [Git and GitHub Glossary](#git-and-github-glossary)
- [FAQ English](#faq-english)

---

---

## Version Française

---

### A propos de ce guide

Ce guide s'adresse aux personnes qui débutent en informatique, aux étudiants en première année de développement, et à toute personne souhaitant comprendre Git et GitHub de façon concrète et progressive. Aucune connaissance préalable n'est requise pour commencer.

Git est un outil de gestion de version. GitHub est une plateforme en ligne qui héberge des dépôts Git. Les deux ne sont pas la même chose, mais ils fonctionnent ensemble. Ce guide vous explique comment les utiliser efficacement, depuis l'installation jusqu'aux pratiques professionnelles.

Cheat sheet visuelle (image) disponible dans ce dépôt :

![GitHub Cheat Sheet](img/GitHub-Cheat-Sheet-IMG-FR.jpg)

Cheat sheet PDF téléchargeable : [Git-Cheat-Sheet_FR.pdf](Git-Cheat-Sheet_FR.pdf)

---

### Prérequis

Avant de commencer, vous avez besoin de :

- Un compte GitHub gratuit : [https://github.com/join](https://github.com/join)
- Git installé sur votre machine : [https://git-scm.com/downloads](https://git-scm.com/downloads)
- Un terminal (invite de commandes, PowerShell, bash, zsh...)
- Un éditeur de code (Visual Studio Code est recommandé pour les débutants) : [https://code.visualstudio.com/](https://code.visualstudio.com/)

---

### Comprendre Git et GitHub

**Git** est un logiciel libre installé localement sur votre ordinateur. Il permet de suivre l'historique de vos fichiers, de travailler sur plusieurs versions en parallèle et de revenir en arrière si besoin.

**GitHub** est un site web qui héberge vos dépôts Git en ligne. Il permet de collaborer avec d'autres personnes, de rendre votre code public ou privé, et d'utiliser des outils comme les Issues, les Pull Requests ou les GitHub Actions.

| Concept | Git | GitHub |
|---|---|---|
| Type | Logiciel local | Plateforme en ligne |
| Rôle | Gestion de version | Hébergement et collaboration |
| Fonctionne sans internet | Oui | Non |
| Gratuit | Oui | Oui (avec options payantes) |

**Autres alternatives à GitHub** (si vous êtes curieux) :

- [GitLab](https://gitlab.com/) : similaire à GitHub, très utilisé en entreprise
- [Bitbucket](https://bitbucket.org/) : utilisé souvent avec les outils Atlassian

---

### Installation et configuration

#### Installer Git

Rendez-vous sur [https://git-scm.com/downloads](https://git-scm.com/downloads) et téléchargez la version correspondant à votre système d'exploitation (Windows, macOS, Linux).

Vérifiez l'installation en ouvrant un terminal et en tapant :

```bash
git --version
```

Vous devriez voir quelque chose comme `git version 2.43.0`.

#### Configurer votre identité

Avant d'utiliser Git, vous devez indiquer votre nom et votre adresse e-mail. Ces informations apparaîtront dans chaque commit que vous créerez.

```bash
git config --global user.name "Votre Nom"
git config --global user.email "votre@email.com"
```

#### Configurer l'éditeur par défaut (optionnel)

```bash
# Pour utiliser Visual Studio Code comme éditeur Git
git config --global core.editor "code --wait"

# Pour utiliser nano (plus simple en terminal)
git config --global core.editor "nano"
```

#### Vérifier votre configuration

```bash
git config --list
```

#### Configurer l'authentification SSH (recommandé)

L'authentification SSH est plus sécurisée et plus pratique que le mot de passe. Elle vous évite de saisir vos identifiants à chaque opération.

```bash
# Générer une clé SSH
ssh-keygen -t ed25519 -C "votre@email.com"

# Afficher la clé publique à copier dans GitHub
cat ~/.ssh/id_ed25519.pub
```

Ensuite, allez dans GitHub > Settings > SSH and GPG keys > New SSH key et collez votre clé.

Documentation officielle SSH : [https://docs.github.com/fr/authentication/connecting-to-github-with-ssh](https://docs.github.com/fr/authentication/connecting-to-github-with-ssh)

---

### Structure d'un dépôt professionnel

Une bonne structure de dépôt facilite la lecture, la maintenance et la collaboration. Voici la structure recommandée, utilisée dans la majorité des projets professionnels :

```
mon-projet/
├── .github/
│   ├── workflows/            # Fichiers GitHub Actions (CI/CD)
│   │   └── ci.yml
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md
│   │   └── feature_request.md
│   └── PULL_REQUEST_TEMPLATE.md
├── docs/                     # Documentation détaillée
│   └── architecture.md
├── src/                      # Code source principal
│   ├── main/                 # Code de production
│   └── test/                 # Tests automatisés
├── scripts/                  # Scripts utilitaires
├── img/                      # Images du projet (captures, logos, cheat sheets...)
├── build/                    # Fichiers de compilation (souvent dans .gitignore)
├── dist/                     # Fichiers distribuables (optionnel)
├── .gitignore                # Fichiers à ignorer dans Git
├── .editorconfig             # Configuration de l'éditeur
├── LICENSE                   # Licence du projet
├── README.md                 # Fichier principal de présentation
├── CONTRIBUTING.md           # Guide de contribution
├── CHANGELOG.md              # Historique des changements
├── SECURITY.md               # Politique de sécurité
└── CODE_OF_CONDUCT.md        # Code de conduite
```

#### Rôle de chaque élément

**Le dossier .github/**

Ce dossier est reconnu automatiquement par GitHub. Il contient la configuration propre à la plateforme. Le sous-dossier `workflows/` contient les automatisations (CI/CD). Le sous-dossier `ISSUE_TEMPLATE/` contient les modèles de tickets. Le fichier `PULL_REQUEST_TEMPLATE.md` est le modèle affiché quand quelqu'un ouvre une Pull Request.

**Le dossier docs/**

La documentation détaillée du projet : architecture, décisions techniques, guides d'utilisation, spécifications. Ce dossier peut aussi alimenter GitHub Pages pour générer un site web statique.

**Le dossier src/**

Le code source de l'application. Il est classique de séparer `main/` (code de production) et `test/` (tests).

**Le dossier scripts/**

Scripts d'automatisation, de déploiement, d'analyse ou de maintenance.

**Les fichiers racine**

Ces fichiers sont placés à la racine car GitHub les reconnaît et les affiche automatiquement.

---

### Créer sa structure depuis l'interface web GitHub

Cette méthode est idéale si vous débutez ou si vous n'avez pas encore Git installé localement.

#### Etape 1 : Créer un nouveau dépôt

1. Allez sur [https://github.com/new](https://github.com/new)
2. Remplissez le nom du dépôt
3. Ajoutez une description courte
4. Choisissez Public ou Private
5. Cochez "Add a README file"
6. Choisissez un fichier `.gitignore` selon votre langage
7. Choisissez une licence (MIT pour commencer)
8. Cliquez sur "Create repository"

#### Etape 2 : Créer des fichiers et dossiers

Pour créer un fichier dans un dossier qui n'existe pas encore, cliquez sur "Add file" > "Create new file" et tapez directement le chemin avec le `/`. Par exemple, entrez `docs/architecture.md` pour créer le fichier `architecture.md` dans le dossier `docs/`.

GitHub crée automatiquement les dossiers intermédiaires.

#### Etape 3 : Ajouter un fichier CONTRIBUTING.md

Cliquez sur "Add file" > "Create new file" et nommez-le `CONTRIBUTING.md`.

#### Etape 4 : Créer les templates d'issues

Cliquez sur "Add file" > "Create new file" et entrez le chemin `.github/ISSUE_TEMPLATE/bug_report.md`.

#### Etape 5 : Configurer GitHub Actions

Cliquez sur "Add file" > "Create new file" et entrez `.github/workflows/ci.yml`.

#### Etape 6 : Configurer les labels

Dans l'onglet "Issues", cliquez sur "Labels" pour gérer vos labels. Les labels recommandés sont :

| Label | Description |
|---|---|
| bug | Quelque chose ne fonctionne pas |
| enhancement | Nouvelle fonctionnalité |
| documentation | Amélioration de la documentation |
| good first issue | Idéal pour une première contribution |
| help wanted | Aide externe souhaitée |
| question | Demande d'information |
| wontfix | Ce problème ne sera pas traité |
| duplicate | Ce problème a déjà été signalé |

---

### Créer sa structure depuis la ligne de commande

#### Initialiser un nouveau projet

```bash
# Créer le dossier du projet et entrer dedans
mkdir mon-projet
cd mon-projet

# Initialiser le dépôt Git
git init
```

#### Créer la structure complète en une seule commande

```bash
mkdir -p .github/{workflows,ISSUE_TEMPLATE} docs src/{main,test} scripts img build dist
```

#### Créer les fichiers de base

```bash
touch .gitignore LICENSE README.md CONTRIBUTING.md CHANGELOG.md SECURITY.md CODE_OF_CONDUCT.md
touch .github/PULL_REQUEST_TEMPLATE.md
touch .github/ISSUE_TEMPLATE/bug_report.md
touch .github/ISSUE_TEMPLATE/feature_request.md
touch .github/workflows/ci.yml
touch docs/architecture.md
```

#### Créer un .gitignore complet

```bash
cat > .gitignore << 'EOF'
# Dépendances
node_modules/
vendor/
.venv/

# Build
build/
dist/
*.class
*.jar
*.war
*.ear

# Logs
*.log
*.tmp
*.swp

# Environnement
.env
.env.local
.env.production

# IDE
.idea/
*.iml
.vscode/
*.suo
*.ntvs*
*.njsproj
*.sln

# OS
.DS_Store
Thumbs.db

# Tests
coverage/
.nyc_output/
EOF
```

#### Effectuer le premier commit

```bash
# Ajouter tous les fichiers
git add .

# Créer le premier commit
git commit -m "feat: initial project structure"

# Connecter au dépôt GitHub (remplacez avec votre URL)
git remote add origin git@github.com:votre-utilisateur/mon-projet.git

# Envoyer sur GitHub
git push -u origin main
```

---

### Commandes Git essentielles

Pour la documentation complète et toujours à jour : [https://git-scm.com/docs](https://git-scm.com/docs)

#### Initialiser et cloner

```bash
# Initialiser un dépôt dans le dossier courant
git init

# Cloner un dépôt distant
git clone https://github.com/utilisateur/depot.git

# Cloner dans un dossier avec un nom spécifique
git clone https://github.com/utilisateur/depot.git mon-dossier
```

#### Etat et historique

```bash
# Voir l'état du dépôt (fichiers modifiés, staged, etc.)
git status

# Voir l'historique des commits
git log

# Voir l'historique de façon compacte
git log --oneline

# Voir l'historique avec représentation graphique des branches
git log --oneline --graph --all

# Voir les différences entre le working directory et le staging
git diff

# Voir les différences pour les fichiers staged
git diff --staged
```

#### Ajouter et commiter

```bash
# Ajouter un fichier au staging
git add nom-du-fichier.txt

# Ajouter tous les fichiers modifiés
git add .

# Créer un commit
git commit -m "message de commit"

# Ajouter et commiter en une commande (fichiers déjà trackés uniquement)
git commit -am "message de commit"

# Modifier le message du dernier commit (avant push uniquement)
git commit --amend -m "nouveau message"
```

#### Branches

```bash
# Lister les branches locales
git branch

# Lister toutes les branches (locales et distantes)
git branch -a

# Créer une nouvelle branche
git branch nom-de-branche

# Passer sur une branche existante
git checkout nom-de-branche

# Créer une branche et y passer directement (recommandé)
git checkout -b nom-de-branche

# Méthode moderne (Git 2.23+)
git switch -c nom-de-branche

# Supprimer une branche locale
git branch -d nom-de-branche

# Forcer la suppression d'une branche locale
git branch -D nom-de-branche
```

#### Synchroniser avec le dépôt distant

```bash
# Récupérer les changements distants sans fusionner
git fetch

# Récupérer et fusionner les changements distants
git pull

# Envoyer les commits sur le dépôt distant
git push

# Premier push d'une branche
git push -u origin nom-de-branche

# Supprimer une branche distante
git push origin --delete nom-de-branche
```

#### Fusionner et rebaser

```bash
# Fusionner une branche dans la branche courante
git merge nom-de-branche

# Rebaser la branche courante sur une autre
git rebase main

# Annuler un merge en cours
git merge --abort

# Annuler un rebase en cours
git rebase --abort
```

#### Stash (remiser temporairement)

```bash
# Mettre de côté les modifications en cours
git stash

# Lister les stash
git stash list

# Réappliquer le dernier stash
git stash pop

# Réappliquer sans supprimer le stash
git stash apply
```

#### Tags

```bash
# Créer un tag sur le commit courant
git tag v1.0.0

# Créer un tag annoté (recommandé pour les releases)
git tag -a v1.0.0 -m "Version 1.0.0"

# Lister les tags
git tag

# Pousser les tags vers GitHub
git push origin --tags
```

#### Revenir en arrière

```bash
# Désindexer un fichier (enlever du staging)
git reset HEAD nom-du-fichier.txt

# Annuler les modifications d'un fichier (revenir à la version committée)
git checkout -- nom-du-fichier.txt

# Revenir au commit précédent (sans effacer l'historique)
git revert HEAD

# Réinitialiser au commit d'un certain hash (dangereux, modifie l'historique)
git reset --hard abc1234
```

---

### Branches et workflow

#### Le modèle Git Flow

Git Flow est une convention d'organisation des branches qui structure le travail en équipe. Ce n'est pas une obligation, mais c'est une bonne référence pour les projets professionnels.

| Branche | Rôle |
|---|---|
| `main` | Version stable en production |
| `develop` | Développement en cours, intégration |
| `feature/nom` | Développement d'une nouvelle fonctionnalité |
| `fix/nom` | Correction de bug |
| `hotfix/nom` | Correction urgente en production |
| `release/1.0.0` | Préparation d'une version |

#### Workflow type pour une fonctionnalité

```bash
# Partir toujours depuis develop à jour
git checkout develop
git pull

# Créer la branche de fonctionnalité
git checkout -b feature/ma-fonctionnalite

# ... travailler, commiter ...

# Mettre à jour par rapport à develop avant de merger
git fetch origin
git rebase origin/develop

# Ouvrir une Pull Request sur GitHub depuis feature/ma-fonctionnalite vers develop
```

#### Pull Requests

Une Pull Request (PR) est une demande d'intégration de votre branche dans une autre. C'est le coeur du travail collaboratif sur GitHub. Elle permet à l'équipe de relire le code, de faire des commentaires, et de valider les changements avant qu'ils n'arrivent sur la branche principale.

**Bonnes pratiques pour une Pull Request :**

- Donner un titre clair et descriptif
- Décrire ce que fait le changement et pourquoi
- Référencer les issues liées avec `Closes #42` ou `Fixes #42`
- Garder la PR aussi petite et ciblée que possible
- Répondre aux commentaires de revue de façon constructive

---

### Messages de commit

Un bon message de commit explique clairement ce qui a été fait et pourquoi. La convention la plus répandue est **Conventional Commits** : [https://www.conventionalcommits.org/fr/](https://www.conventionalcommits.org/fr/)

#### Format

```
type(scope): description courte

Corps optionnel : explication plus détaillée.

Footer optionnel : références aux issues, breaking changes...
```

#### Types de commit

| Type | Utilisation |
|---|---|
| `feat` | Nouvelle fonctionnalité |
| `fix` | Correction de bug |
| `docs` | Modification de documentation |
| `style` | Formatage, espaces (pas de changement de logique) |
| `refactor` | Refactoring sans changement de comportement |
| `test` | Ajout ou modification de tests |
| `chore` | Tâches de maintenance, dépendances |
| `perf` | Amélioration de performance |
| `ci` | Changements liés à l'intégration continue |
| `build` | Changements de build system |
| `revert` | Annulation d'un commit précédent |

#### Exemples

```
feat(auth): add email verification on registration

fix(api): correct HTTP status code on 404 responses

docs: update installation steps in README

chore(deps): update dependencies to latest versions

feat(user): add profile picture upload

Closes #42
```

---

### GitHub Actions et CI/CD

GitHub Actions est le système d'automatisation intégré à GitHub. Il permet de déclencher des actions automatiques sur des événements (push, pull request, déploiement, etc.).

Documentation officielle : [https://docs.github.com/fr/actions](https://docs.github.com/fr/actions)

#### Exemple de workflow CI basique

Ce fichier doit être placé dans `.github/workflows/ci.yml` :

```yaml
name: CI

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main, develop ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout du code
        uses: actions/checkout@v4

      - name: Configurer Node.js
        uses: actions/setup-node@v4
        with:
          node-version: '20'

      - name: Installer les dépendances
        run: npm install

      - name: Lancer les tests
        run: npm test

      - name: Vérifier le style de code
        run: npm run lint
```

#### Exemple pour un projet PHP/Symfony

```yaml
name: CI PHP

on: [push, pull_request]

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - name: Configurer PHP
        uses: shivammathur/setup-php@v2
        with:
          php-version: '8.3'

      - name: Installer les dépendances Composer
        run: composer install

      - name: Lancer PHPStan
        run: vendor/bin/phpstan analyse

      - name: Lancer les tests PHPUnit
        run: vendor/bin/phpunit
```

#### Principaux déclencheurs (triggers)

| Déclencheur | Description |
|---|---|
| `push` | A chaque push sur une branche |
| `pull_request` | A l'ouverture ou la mise à jour d'une PR |
| `schedule` | Selon un planning cron |
| `workflow_dispatch` | Déclenchement manuel |
| `release` | A la création d'une release |

---

### Contribuer à un projet open source

L'open source est au coeur de l'écosystème du développement. Contribuer à un projet existant est une excellente façon d'apprendre, de se faire connaître et de donner en retour à la communauté.

Guide officiel GitHub sur les contributions : [https://docs.github.com/fr/get-started/exploring-projects-on-github/contributing-to-a-project](https://docs.github.com/fr/get-started/exploring-projects-on-github/contributing-to-a-project)

#### Etapes pour contribuer

**1. Trouver un projet**

- Parcourez [https://github.com/explore](https://github.com/explore)
- Cherchez des issues labelisées `good first issue` ou `help wanted`
- Consultez [https://goodfirstissue.dev/](https://goodfirstissue.dev/)
- Consultez [https://up-for-grabs.net/](https://up-for-grabs.net/)

**2. Forker le dépôt**

Le fork crée une copie du dépôt sur votre compte GitHub. Cliquez sur le bouton "Fork" en haut à droite de la page du projet.

**3. Cloner votre fork**

```bash
git clone git@github.com:votre-utilisateur/le-projet.git
cd le-projet
```

**4. Ajouter le dépôt original comme remote**

```bash
git remote add upstream git@github.com:auteur-original/le-projet.git
```

**5. Créer une branche pour votre contribution**

```bash
git checkout -b feature/ma-contribution
```

**6. Faire vos modifications et commiter**

```bash
git add .
git commit -m "feat: add my contribution"
```

**7. Mettre à jour votre fork avec les dernières modifications de l'original**

```bash
git fetch upstream
git rebase upstream/main
```

**8. Pousser et ouvrir une Pull Request**

```bash
git push origin feature/ma-contribution
```

Ensuite allez sur GitHub et ouvrez une Pull Request depuis votre branche vers la branche principale du projet original.

**9. Répondre aux retours**

Le mainteneur du projet relira votre code et pourra demander des modifications. Restez ouvert aux retours, c'est normal et constructif.

#### Points d'attention

- Lisez toujours le fichier `CONTRIBUTING.md` avant de commencer
- Vérifiez qu'il n'existe pas déjà une issue ou une PR pour ce que vous voulez faire
- Respectez le style de code du projet
- Ecrivez des tests si le projet en a
- Soyez patient : les mainteneurs sont souvent bénévoles

---

### Fichiers importants d'un dépôt

| Fichier | Rôle | Obligatoire |
|---|---|---|
| `README.md` | Présentation du projet | Fortement recommandé |
| `LICENSE` | Licence d'utilisation | Oui pour l'open source |
| `CONTRIBUTING.md` | Guide de contribution | Recommandé |
| `CHANGELOG.md` | Historique des versions | Recommandé |
| `SECURITY.md` | Comment signaler une faille | Recommandé |
| `CODE_OF_CONDUCT.md` | Règles de comportement | Recommandé |
| `.gitignore` | Fichiers ignorés par Git | Oui |
| `.editorconfig` | Config de l'éditeur pour tous | Optionnel |

#### Les licences les plus courantes

| Licence | Utilisation | Lien |
|---|---|---|
| MIT | Très permissive, usage libre | [opensource.org/licenses/MIT](https://opensource.org/licenses/MIT) |
| Apache 2.0 | Permissive, mention de brevets | [apache.org/licenses/LICENSE-2.0](https://www.apache.org/licenses/LICENSE-2.0) |
| GPL v3 | Copyleft, le code dérivé doit rester libre | [gnu.org/licenses/gpl-3.0](https://www.gnu.org/licenses/gpl-3.0.html) |
| AGPL v3 | Comme GPL mais aussi pour les services web | [gnu.org/licenses/agpl-3.0](https://www.gnu.org/licenses/agpl-3.0.html) |
| LGPL | Permissive pour les bibliothèques | [gnu.org/licenses/lgpl-3.0](https://www.gnu.org/licenses/lgpl-3.0.html) |
| ISC | Similaire à MIT, très courte | [opensource.org/licenses/ISC](https://opensource.org/licenses/ISC) |

Outil pour choisir une licence : [https://choosealicense.com/](https://choosealicense.com/)

---

### Badges GitHub

Les badges sont de petites images affichées dans le README. Ils communiquent des informations importantes en un coup d'oeil : statut de build, version, licence, couverture de tests...

Générateur de badges : [https://shields.io/](https://shields.io/)

#### Badges courants

```markdown
# Statut de CI
[![CI](https://github.com/utilisateur/depot/actions/workflows/ci.yml/badge.svg)](https://github.com/utilisateur/depot/actions)

# Licence
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

# Version
[![Version](https://img.shields.io/badge/version-1.0.0-blue)](https://github.com/utilisateur/depot/releases)

# Couverture de tests
[![Coverage](https://img.shields.io/codecov/c/github/utilisateur/depot)](https://codecov.io/gh/utilisateur/depot)

# PRs bienvenues
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

# Stars GitHub
[![GitHub stars](https://img.shields.io/github/stars/utilisateur/depot?style=social)](https://github.com/utilisateur/depot/stargazers)

# Dernière version publiée
[![GitHub release](https://img.shields.io/github/v/release/utilisateur/depot)](https://github.com/utilisateur/depot/releases)

# Dernier commit
[![GitHub last commit](https://img.shields.io/github/last-commit/utilisateur/depot)](https://github.com/utilisateur/depot/commits/main)
```

---

### Ressources et liens

#### Documentation officielle

- Documentation GitHub (EN) : [https://docs.github.com/en](https://docs.github.com/en)
- Documentation GitHub (FR) : [https://docs.github.com/fr](https://docs.github.com/fr)
- Documentation Git officielle : [https://git-scm.com/doc](https://git-scm.com/doc)
- Pro Git (livre libre en FR) : [https://git-scm.com/book/fr/v2](https://git-scm.com/book/fr/v2)

#### Syntaxe Markdown

- GitHub Markdown (EN) : [https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- GitHub Markdown (FR) : [https://docs.github.com/fr/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax](https://docs.github.com/fr/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- Référence Markdown complète : [https://www.markdownguide.org/](https://www.markdownguide.org/)

#### Apprendre Git de façon interactive

- Apprendre Git dans le navigateur : [https://learngitbranching.js.org/?locale=fr_FR](https://learngitbranching.js.org/?locale=fr_FR)
- GitHub Skills : [https://skills.github.com/](https://skills.github.com/)
- Git Immersion : [https://gitimmersion.com/](https://gitimmersion.com/)

#### Conventions et bonnes pratiques

- Conventional Commits : [https://www.conventionalcommits.org/fr/](https://www.conventionalcommits.org/fr/)
- Git Flow : [https://nvie.com/posts/a-successful-git-branching-model/](https://nvie.com/posts/a-successful-git-branching-model/)
- GitHub Flow : [https://docs.github.com/fr/get-started/using-github/github-flow](https://docs.github.com/fr/get-started/using-github/github-flow)
- Trunk Based Development : [https://trunkbaseddevelopment.com/](https://trunkbaseddevelopment.com/)
- Semantic Versioning : [https://semver.org/lang/fr/](https://semver.org/lang/fr/)

#### Outils utiles

- Générateur de .gitignore : [https://gitignore.io/](https://gitignore.io/) ou [https://www.toptal.com/developers/gitignore](https://www.toptal.com/developers/gitignore)
- Choisir une licence : [https://choosealicense.com/](https://choosealicense.com/)
- Générateur de badges : [https://shields.io/](https://shields.io/)
- GitHub CLI : [https://cli.github.com/](https://cli.github.com/)
- GitKraken (GUI Git) : [https://www.gitkraken.com/](https://www.gitkraken.com/)
- GitHub Desktop : [https://desktop.github.com/](https://desktop.github.com/)
- Résolution de conflits visuels : [https://code.visualstudio.com/docs/sourcecontrol/overview](https://code.visualstudio.com/docs/sourcecontrol/overview)

#### Trouver des projets open source pour contribuer

- GitHub Explore : [https://github.com/explore](https://github.com/explore)
- Good First Issues : [https://goodfirstissue.dev/](https://goodfirstissue.dev/)
- Up For Grabs : [https://up-for-grabs.net/](https://up-for-grabs.net/)
- First Timers Only : [https://www.firsttimersonly.com/](https://www.firsttimersonly.com/)
- Open Source Guide : [https://opensource.guide/fr/](https://opensource.guide/fr/)

#### Sécurité

- GitHub Security : [https://docs.github.com/fr/code-security](https://docs.github.com/fr/code-security)
- Dependabot : [https://docs.github.com/fr/code-security/dependabot](https://docs.github.com/fr/code-security/dependabot)

---

### Lexique Git et GitHub

| Terme | Définition |
|---|---|
| **Repository (dépôt)** | Espace de stockage contenant tout le code et l'historique d'un projet |
| **Clone** | Copie locale complète d'un dépôt distant |
| **Fork** | Copie d'un dépôt sur son propre compte GitHub |
| **Branch (branche)** | Version parallèle du code permettant de travailler sans affecter la branche principale |
| **Commit** | Enregistrement d'un ensemble de modifications dans l'historique |
| **Staging (index)** | Zone intermédiaire où l'on prépare les fichiers avant de commiter |
| **Push** | Envoi des commits locaux vers le dépôt distant |
| **Pull** | Récupération et fusion des commits distants en local |
| **Fetch** | Récupération des commits distants sans fusion |
| **Merge** | Fusion de deux branches |
| **Rebase** | Réécriture de l'historique pour intégrer des modifications d'une autre branche |
| **Pull Request (PR)** | Demande d'intégration d'une branche dans une autre, avec revue de code |
| **Issue** | Ticket signalant un bug, une idée ou une tâche |
| **README** | Fichier de présentation principal d'un dépôt |
| **CONTRIBUTING** | Fichier expliquant comment contribuer au projet |
| **LICENSE** | Fichier définissant les droits d'utilisation du code |
| **CI/CD** | Intégration Continue / Déploiement Continu, automatisation du cycle de développement |
| **GitHub Actions** | Système d'automatisation intégré à GitHub |
| **Workflow** | Fichier YAML définissant une automatisation GitHub Actions |
| **Tag** | Marqueur sur un commit, souvent utilisé pour les versions (v1.0.0) |
| **Release** | Publication officielle d'une version d'un projet sur GitHub |
| **Stash** | Sauvegarde temporaire de modifications non commitées |
| **Conflict** | Situation où deux branches ont modifié le même endroit d'un fichier |
| **Remote** | Dépôt distant (par opposition au dépôt local) |
| **Origin** | Nom conventionnel du remote principal (votre fork ou dépôt) |
| **Upstream** | Nom conventionnel du dépôt original quand on travaille sur un fork |
| **HEAD** | Pointeur indiquant le commit courant |
| **Gitignore** | Fichier listant les patterns de fichiers à ne pas tracker avec Git |
| **Semantic Versioning** | Convention de numérotation de version : MAJEUR.MINEUR.PATCH |
| **Open Source** | Logiciel dont le code source est disponible publiquement |
| **Maintainer** | Personne responsable de la maintenance d'un projet open source |

---

### FAQ Français

**Q : Quelle est la différence entre `git pull` et `git fetch` ?**

`git fetch` télécharge les nouvelles données du dépôt distant mais ne les fusionne pas dans votre branche locale. `git pull` fait la même chose mais fusionne automatiquement. En pratique, `git fetch` suivi de `git rebase` est souvent préféré car il donne plus de contrôle.

**Q : Je me suis trompé dans mon dernier message de commit, comment le corriger ?**

Si vous n'avez pas encore poussé le commit, utilisez `git commit --amend -m "nouveau message"`. Si vous avez déjà poussé, c'est plus délicat car cela modifie l'historique. Il vaut mieux créer un nouveau commit correctif dans ce cas.

**Q : Comment annuler un commit qui a déjà été poussé ?**

Utilisez `git revert HEAD` pour créer un nouveau commit qui annule le précédent, sans modifier l'historique. C'est la méthode sûre. Evitez `git reset --hard` sur des commits déjà partagés avec d'autres personnes.

**Q : Que faire quand j'ai un conflit lors d'un merge ?**

Git marque les conflits dans les fichiers avec des indicateurs `<<<<<<<`, `=======`, `>>>>>>>`. Ouvrez les fichiers concernés, choisissez quelle version garder (ou combinez les deux), supprimez les marqueurs, puis faites `git add` et `git commit` pour finaliser la fusion. Visual Studio Code dispose d'un bon outil visuel pour résoudre les conflits.

**Q : Faut-il commiter le dossier `node_modules/` ?**

Non, jamais. Le dossier `node_modules/` contient les dépendances et peut peser plusieurs centaines de mégaoctets. Il doit être dans le `.gitignore`. Les dépendances se réinstallent avec `npm install` à partir du fichier `package.json`.

**Q : Quelle est la différence entre un fork et un clone ?**

Un fork est une copie d'un dépôt sur votre compte GitHub (côté serveur). Un clone est une copie locale sur votre ordinateur. Pour contribuer à un projet dont vous n'êtes pas collaborateur, vous forkez d'abord le dépôt sur GitHub, puis vous clonez votre fork localement.

**Q : Quand utiliser `merge` vs `rebase` ?**

`merge` préserve l'historique complet et est plus sûr pour les branches partagées. `rebase` réécrit l'historique pour le rendre plus linéaire et lisible, mais ne doit pas être utilisé sur des branches partagées avec d'autres. Pour les branches personnelles de fonctionnalité, `rebase` est souvent préféré. Pour les merges de PR sur main, les deux sont valides selon la convention du projet.

**Q : Comment savoir quelle branche est la branche principale ?**

Sur GitHub, la branche principale est indiquée dans les paramètres du dépôt et visible sur la page d'accueil. Historiquement nommée `master`, elle est aujourd'hui souvent renommée `main`. Sur votre dépôt local : `git branch -a` vous liste toutes les branches.

**Q : Comment créer une release GitHub ?**

Allez dans l'onglet "Releases" de votre dépôt, cliquez sur "Create a new release", choisissez ou créez un tag (ex : `v1.0.0`), ajoutez un titre et une description, puis publiez.

**Q : Peut-on travailler avec Git sans ligne de commande ?**

Oui. GitHub Desktop ([https://desktop.github.com/](https://desktop.github.com/)) offre une interface graphique complète. Visual Studio Code intègre aussi un panneau Git. GitKraken ([https://www.gitkraken.com/](https://www.gitkraken.com/)) est une autre option populaire.

---

---

## English Version

---

### About this guide

This guide is aimed at people who are new to programming, first-year development students, and anyone who wants to understand Git and GitHub in a practical and progressive way. No prior knowledge is required to get started.

Git is a version control tool. GitHub is an online platform that hosts Git repositories. The two are not the same thing, but they work together. This guide explains how to use them effectively, from installation to professional practices.

Visual cheat sheet (image) available in this repository :

![GitHub Cheat Sheet](img/GitHub-Cheat-Sheet-IMG-FR.jpg)

Downloadable PDF cheat sheet : [Git-Cheat-Sheet_FR.pdf](Git-Cheat-Sheet_FR.pdf)

---

### Prerequisites

Before starting, you need :

- A free GitHub account : [https://github.com/join](https://github.com/join)
- Git installed on your machine : [https://git-scm.com/downloads](https://git-scm.com/downloads)
- A terminal (command prompt, PowerShell, bash, zsh...)
- A code editor (Visual Studio Code is recommended for beginners) : [https://code.visualstudio.com/](https://code.visualstudio.com/)

---

### Understanding Git and GitHub

**Git** is open-source software installed locally on your computer. It allows you to track the history of your files, work on multiple versions in parallel, and roll back changes if needed.

**GitHub** is a website that hosts your Git repositories online. It allows you to collaborate with other people, make your code public or private, and use tools like Issues, Pull Requests, and GitHub Actions.

| Concept | Git | GitHub |
|---|---|---|
| Type | Local software | Online platform |
| Role | Version management | Hosting and collaboration |
| Works without internet | Yes | No |
| Free | Yes | Yes (with paid options) |

**Other alternatives to GitHub** (if you are curious) :

- [GitLab](https://gitlab.com/) : similar to GitHub, widely used in enterprise
- [Bitbucket](https://bitbucket.org/) : often used with Atlassian tools

---

### Installation and configuration

#### Installing Git

Go to [https://git-scm.com/downloads](https://git-scm.com/downloads) and download the version matching your operating system (Windows, macOS, Linux).

Verify the installation by opening a terminal and typing :

```bash
git --version
```

You should see something like `git version 2.43.0`.

#### Configuring your identity

Before using Git, you need to set your name and email address. This information will appear in every commit you create.

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

#### Setting the default editor (optional)

```bash
# Use Visual Studio Code as Git editor
git config --global core.editor "code --wait"

# Use nano (simpler in terminal)
git config --global core.editor "nano"
```

#### Check your configuration

```bash
git config --list
```

#### Configure SSH authentication (recommended)

SSH authentication is more secure and convenient than using a password. It avoids entering your credentials on every operation.

```bash
# Generate an SSH key
ssh-keygen -t ed25519 -C "your@email.com"

# Display the public key to copy into GitHub
cat ~/.ssh/id_ed25519.pub
```

Then go to GitHub > Settings > SSH and GPG keys > New SSH key and paste your key.

Official SSH documentation : [https://docs.github.com/en/authentication/connecting-to-github-with-ssh](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

---

### Professional repository structure

A good repository structure makes it easier to read, maintain, and collaborate. Here is the recommended structure, used in the majority of professional projects :

```
my-project/
├── .github/
│   ├── workflows/            # GitHub Actions files (CI/CD)
│   │   └── ci.yml
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md
│   │   └── feature_request.md
│   └── PULL_REQUEST_TEMPLATE.md
├── docs/                     # Detailed documentation
│   └── architecture.md
├── src/                      # Main source code
│   ├── main/                 # Production code
│   └── test/                 # Automated tests
├── scripts/                  # Utility scripts
├── img/                      # Project images (screenshots, logos, cheat sheets...)
├── build/                    # Build files (often in .gitignore)
├── dist/                     # Distributable files (optional)
├── .gitignore                # Files to ignore in Git
├── .editorconfig             # Editor configuration
├── LICENSE                   # Project license
├── README.md                 # Main presentation file
├── CONTRIBUTING.md           # Contribution guide
├── CHANGELOG.md              # Version history
├── SECURITY.md               # Security policy
└── CODE_OF_CONDUCT.md        # Code of conduct
```

#### Role of each element

**The .github/ folder**

This folder is automatically recognized by GitHub. It contains configuration specific to the platform. The `workflows/` subfolder contains automations (CI/CD). The `ISSUE_TEMPLATE/` subfolder contains issue templates. The `PULL_REQUEST_TEMPLATE.md` file is the template displayed when someone opens a Pull Request.

**The docs/ folder**

Detailed project documentation : architecture, technical decisions, usage guides, specifications. This folder can also feed GitHub Pages to generate a static website.

**The src/ folder**

The application source code. It is common practice to separate `main/` (production code) and `test/` (tests).

**The scripts/ folder**

Automation, deployment, analysis, or maintenance scripts.

**Root files**

These files are placed at the root because GitHub recognizes and displays them automatically.

---

### Creating structure from the GitHub web interface

This method is ideal if you are just starting out or do not yet have Git installed locally.

#### Step 1 : Create a new repository

1. Go to [https://github.com/new](https://github.com/new)
2. Fill in the repository name
3. Add a short description
4. Choose Public or Private
5. Check "Add a README file"
6. Choose a `.gitignore` file based on your language
7. Choose a license (MIT to start with)
8. Click "Create repository"

#### Step 2 : Create files and folders

To create a file in a folder that does not yet exist, click "Add file" > "Create new file" and type the path directly with `/`. For example, enter `docs/architecture.md` to create the file `architecture.md` in the `docs/` folder.

GitHub automatically creates intermediate folders.

#### Step 3 : Add a CONTRIBUTING.md file

Click "Add file" > "Create new file" and name it `CONTRIBUTING.md`.

#### Step 4 : Create issue templates

Click "Add file" > "Create new file" and enter the path `.github/ISSUE_TEMPLATE/bug_report.md`.

#### Step 5 : Configure GitHub Actions

Click "Add file" > "Create new file" and enter `.github/workflows/ci.yml`.

#### Step 6 : Configure labels

In the "Issues" tab, click "Labels" to manage your labels. Recommended labels :

| Label | Description |
|---|---|
| bug | Something is not working |
| enhancement | New feature |
| documentation | Documentation improvement |
| good first issue | Great for a first contribution |
| help wanted | External help is welcome |
| question | Information request |
| wontfix | This issue will not be addressed |
| duplicate | This issue has already been reported |

---

### Creating structure from the command line

#### Initialize a new project

```bash
# Create the project folder and enter it
mkdir my-project
cd my-project

# Initialize the Git repository
git init
```

#### Create the complete structure in a single command

```bash
mkdir -p .github/{workflows,ISSUE_TEMPLATE} docs src/{main,test} scripts img build dist
```

#### Create the base files

```bash
touch .gitignore LICENSE README.md CONTRIBUTING.md CHANGELOG.md SECURITY.md CODE_OF_CONDUCT.md
touch .github/PULL_REQUEST_TEMPLATE.md
touch .github/ISSUE_TEMPLATE/bug_report.md
touch .github/ISSUE_TEMPLATE/feature_request.md
touch .github/workflows/ci.yml
touch docs/architecture.md
```

#### Create a comprehensive .gitignore

```bash
cat > .gitignore << 'EOF'
# Dependencies
node_modules/
vendor/
.venv/

# Build
build/
dist/
*.class
*.jar
*.war
*.ear

# Logs
*.log
*.tmp
*.swp

# Environment
.env
.env.local
.env.production

# IDE
.idea/
*.iml
.vscode/
*.suo
*.ntvs*
*.njsproj
*.sln

# OS
.DS_Store
Thumbs.db

# Tests
coverage/
.nyc_output/
EOF
```

#### Make the first commit

```bash
# Stage all files
git add .

# Create the first commit
git commit -m "feat: initial project structure"

# Connect to the GitHub repository (replace with your URL)
git remote add origin git@github.com:your-username/my-project.git

# Push to GitHub
git push -u origin main
```

---

### Essential Git commands

For the complete and always up-to-date documentation : [https://git-scm.com/docs](https://git-scm.com/docs)

#### Initialize and clone

```bash
# Initialize a repository in the current folder
git init

# Clone a remote repository
git clone https://github.com/user/repo.git

# Clone into a folder with a specific name
git clone https://github.com/user/repo.git my-folder
```

#### Status and history

```bash
# View the repository status (modified files, staged, etc.)
git status

# View commit history
git log

# View history in compact form
git log --oneline

# View history with branch graph
git log --oneline --graph --all

# View differences between working directory and staging
git diff

# View differences for staged files
git diff --staged
```

#### Stage and commit

```bash
# Add a file to staging
git add filename.txt

# Add all modified files
git add .

# Create a commit
git commit -m "commit message"

# Add and commit in one command (tracked files only)
git commit -am "commit message"

# Amend the last commit message (before push only)
git commit --amend -m "new message"
```

#### Branches

```bash
# List local branches
git branch

# List all branches (local and remote)
git branch -a

# Create a new branch
git branch branch-name

# Switch to an existing branch
git checkout branch-name

# Create a branch and switch to it (recommended)
git checkout -b branch-name

# Modern way (Git 2.23+)
git switch -c branch-name

# Delete a local branch
git branch -d branch-name

# Force delete a local branch
git branch -D branch-name
```

#### Synchronize with the remote repository

```bash
# Fetch remote changes without merging
git fetch

# Fetch and merge remote changes
git pull

# Push commits to the remote repository
git push

# First push of a branch
git push -u origin branch-name

# Delete a remote branch
git push origin --delete branch-name
```

#### Merge and rebase

```bash
# Merge a branch into the current branch
git merge branch-name

# Rebase the current branch onto another
git rebase main

# Abort an in-progress merge
git merge --abort

# Abort an in-progress rebase
git rebase --abort
```

#### Stash (temporarily shelve changes)

```bash
# Stash current changes
git stash

# List stashes
git stash list

# Re-apply the latest stash
git stash pop

# Re-apply without removing the stash
git stash apply
```

#### Tags

```bash
# Create a tag on the current commit
git tag v1.0.0

# Create an annotated tag (recommended for releases)
git tag -a v1.0.0 -m "Version 1.0.0"

# List tags
git tag

# Push tags to GitHub
git push origin --tags
```

#### Roll back changes

```bash
# Unstage a file (remove from staging)
git reset HEAD filename.txt

# Discard file modifications (restore committed version)
git checkout -- filename.txt

# Undo the last commit (without deleting history)
git revert HEAD

# Reset to a specific commit hash (dangerous, rewrites history)
git reset --hard abc1234
```

---

### Branches and workflow

#### The Git Flow model

Git Flow is a branching convention that structures teamwork. It is not mandatory, but it is a solid reference for professional projects.

| Branch | Role |
|---|---|
| `main` | Stable production version |
| `develop` | Ongoing development, integration |
| `feature/name` | Development of a new feature |
| `fix/name` | Bug fix |
| `hotfix/name` | Urgent production fix |
| `release/1.0.0` | Preparing a release |

#### Typical workflow for a feature

```bash
# Always start from an up-to-date develop branch
git checkout develop
git pull

# Create the feature branch
git checkout -b feature/my-feature

# ... work, commit ...

# Update against develop before merging
git fetch origin
git rebase origin/develop

# Open a Pull Request on GitHub from feature/my-feature to develop
```

#### Pull Requests

A Pull Request (PR) is a request to integrate your branch into another one. It is at the heart of collaborative work on GitHub. It allows the team to review the code, leave comments, and validate changes before they reach the main branch.

**Best practices for a Pull Request :**

- Give a clear and descriptive title
- Describe what the change does and why
- Reference related issues with `Closes #42` or `Fixes #42`
- Keep the PR as small and focused as possible
- Respond to review comments constructively

---

### Commit messages

A good commit message clearly explains what was done and why. The most widespread convention is **Conventional Commits** : [https://www.conventionalcommits.org/en/](https://www.conventionalcommits.org/en/v1.0.0/)

#### Format

```
type(scope): short description

Optional body : more detailed explanation.

Optional footer : issue references, breaking changes...
```

#### Commit types

| Type | Usage |
|---|---|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation change |
| `style` | Formatting, spaces (no logic change) |
| `refactor` | Refactoring without behavior change |
| `test` | Adding or modifying tests |
| `chore` | Maintenance tasks, dependencies |
| `perf` | Performance improvement |
| `ci` | Changes related to continuous integration |
| `build` | Build system changes |
| `revert` | Reverting a previous commit |

#### Examples

```
feat(auth): add email verification on registration

fix(api): correct HTTP status code on 404 responses

docs: update installation steps in README

chore(deps): update dependencies to latest versions

feat(user): add profile picture upload

Closes #42
```

---

### GitHub Actions and CI/CD

GitHub Actions is the automation system built into GitHub. It allows you to trigger automatic actions on events (push, pull request, deployment, etc.).

Official documentation : [https://docs.github.com/en/actions](https://docs.github.com/en/actions)

#### Basic CI workflow example

This file must be placed in `.github/workflows/ci.yml` :

```yaml
name: CI

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main, develop ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Set up Node.js
        uses: actions/setup-node@v4
        with:
          node-version: '20'

      - name: Install dependencies
        run: npm install

      - name: Run tests
        run: npm test

      - name: Check code style
        run: npm run lint
```

#### Example for a PHP/Symfony project

```yaml
name: CI PHP

on: [push, pull_request]

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - name: Set up PHP
        uses: shivammathur/setup-php@v2
        with:
          php-version: '8.3'

      - name: Install Composer dependencies
        run: composer install

      - name: Run PHPStan
        run: vendor/bin/phpstan analyse

      - name: Run PHPUnit tests
        run: vendor/bin/phpunit
```

#### Main triggers

| Trigger | Description |
|---|---|
| `push` | On every push to a branch |
| `pull_request` | When a PR is opened or updated |
| `schedule` | On a cron schedule |
| `workflow_dispatch` | Manual trigger |
| `release` | When a release is created |

---

### Contributing to open source

Open source is at the heart of the development ecosystem. Contributing to an existing project is an excellent way to learn, build visibility, and give back to the community.

GitHub official guide on contributions : [https://docs.github.com/en/get-started/exploring-projects-on-github/contributing-to-a-project](https://docs.github.com/en/get-started/exploring-projects-on-github/contributing-to-a-project)

#### Steps to contribute

**1. Find a project**

- Browse [https://github.com/explore](https://github.com/explore)
- Look for issues labeled `good first issue` or `help wanted`
- Check [https://goodfirstissue.dev/](https://goodfirstissue.dev/)
- Check [https://up-for-grabs.net/](https://up-for-grabs.net/)

**2. Fork the repository**

The fork creates a copy of the repository on your GitHub account. Click the "Fork" button at the top right of the project page.

**3. Clone your fork**

```bash
git clone git@github.com:your-username/the-project.git
cd the-project
```

**4. Add the original repository as a remote**

```bash
git remote add upstream git@github.com:original-author/the-project.git
```

**5. Create a branch for your contribution**

```bash
git checkout -b feature/my-contribution
```

**6. Make your changes and commit**

```bash
git add .
git commit -m "feat: add my contribution"
```

**7. Update your fork with the latest changes from the original**

```bash
git fetch upstream
git rebase upstream/main
```

**8. Push and open a Pull Request**

```bash
git push origin feature/my-contribution
```

Then go to GitHub and open a Pull Request from your branch to the original project's main branch.

**9. Respond to feedback**

The project maintainer will review your code and may request changes. Stay open to feedback, it is normal and constructive.

#### Points to keep in mind

- Always read the `CONTRIBUTING.md` file before starting
- Check that there is not already an issue or PR for what you want to do
- Respect the project's code style
- Write tests if the project has them
- Be patient : maintainers are often volunteers

---

### Important repository files

| File | Role | Required |
|---|---|---|
| `README.md` | Project presentation | Strongly recommended |
| `LICENSE` | Usage license | Yes for open source |
| `CONTRIBUTING.md` | Contribution guide | Recommended |
| `CHANGELOG.md` | Version history | Recommended |
| `SECURITY.md` | How to report a vulnerability | Recommended |
| `CODE_OF_CONDUCT.md` | Rules of behavior | Recommended |
| `.gitignore` | Files ignored by Git | Yes |
| `.editorconfig` | Editor config for everyone | Optional |

#### Most common licenses

| License | Usage | Link |
|---|---|---|
| MIT | Very permissive, free use | [opensource.org/licenses/MIT](https://opensource.org/licenses/MIT) |
| Apache 2.0 | Permissive, patent mention | [apache.org/licenses/LICENSE-2.0](https://www.apache.org/licenses/LICENSE-2.0) |
| GPL v3 | Copyleft, derived code must stay free | [gnu.org/licenses/gpl-3.0](https://www.gnu.org/licenses/gpl-3.0.html) |
| AGPL v3 | Like GPL but also for web services | [gnu.org/licenses/agpl-3.0](https://www.gnu.org/licenses/agpl-3.0.html) |
| LGPL | Permissive for libraries | [gnu.org/licenses/lgpl-3.0](https://www.gnu.org/licenses/lgpl-3.0.html) |
| ISC | Similar to MIT, very short | [opensource.org/licenses/ISC](https://opensource.org/licenses/ISC) |

Tool to choose a license : [https://choosealicense.com/](https://choosealicense.com/)

---

### GitHub Badges

Badges are small images displayed in the README. They communicate important information at a glance : build status, version, license, test coverage...

Badge generator : [https://shields.io/](https://shields.io/)

#### Common badges

```markdown
# CI status
[![CI](https://github.com/user/repo/actions/workflows/ci.yml/badge.svg)](https://github.com/user/repo/actions)

# License
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

# Version
[![Version](https://img.shields.io/badge/version-1.0.0-blue)](https://github.com/user/repo/releases)

# Test coverage
[![Coverage](https://img.shields.io/codecov/c/github/user/repo)](https://codecov.io/gh/user/repo)

# PRs welcome
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

# GitHub stars
[![GitHub stars](https://img.shields.io/github/stars/user/repo?style=social)](https://github.com/user/repo/stargazers)

# Latest release
[![GitHub release](https://img.shields.io/github/v/release/user/repo)](https://github.com/user/repo/releases)

# Last commit
[![GitHub last commit](https://img.shields.io/github/last-commit/user/repo)](https://github.com/user/repo/commits/main)
```

---

### Resources and links

#### Official documentation

- GitHub documentation (EN) : [https://docs.github.com/en](https://docs.github.com/en)
- GitHub documentation (FR) : [https://docs.github.com/fr](https://docs.github.com/fr)
- Official Git documentation : [https://git-scm.com/doc](https://git-scm.com/doc)
- Pro Git book (free) : [https://git-scm.com/book/en/v2](https://git-scm.com/book/en/v2)

#### Markdown syntax

- GitHub Markdown (EN) : [https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- GitHub Markdown (FR) : [https://docs.github.com/fr/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax](https://docs.github.com/fr/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- Full Markdown reference : [https://www.markdownguide.org/](https://www.markdownguide.org/)

#### Learn Git interactively

- Learn Git in the browser : [https://learngitbranching.js.org/](https://learngitbranching.js.org/)
- GitHub Skills : [https://skills.github.com/](https://skills.github.com/)
- Git Immersion : [https://gitimmersion.com/](https://gitimmersion.com/)

#### Conventions and best practices

- Conventional Commits : [https://www.conventionalcommits.org/en/v1.0.0/](https://www.conventionalcommits.org/en/v1.0.0/)
- Git Flow : [https://nvie.com/posts/a-successful-git-branching-model/](https://nvie.com/posts/a-successful-git-branching-model/)
- GitHub Flow : [https://docs.github.com/en/get-started/using-github/github-flow](https://docs.github.com/en/get-started/using-github/github-flow)
- Trunk Based Development : [https://trunkbaseddevelopment.com/](https://trunkbaseddevelopment.com/)
- Semantic Versioning : [https://semver.org/](https://semver.org/)

#### Useful tools

- .gitignore generator : [https://gitignore.io/](https://gitignore.io/) or [https://www.toptal.com/developers/gitignore](https://www.toptal.com/developers/gitignore)
- Choose a license : [https://choosealicense.com/](https://choosealicense.com/)
- Badge generator : [https://shields.io/](https://shields.io/)
- GitHub CLI : [https://cli.github.com/](https://cli.github.com/)
- GitKraken (Git GUI) : [https://www.gitkraken.com/](https://www.gitkraken.com/)
- GitHub Desktop : [https://desktop.github.com/](https://desktop.github.com/)
- VS Code source control : [https://code.visualstudio.com/docs/sourcecontrol/overview](https://code.visualstudio.com/docs/sourcecontrol/overview)

#### Find open source projects to contribute to

- GitHub Explore : [https://github.com/explore](https://github.com/explore)
- Good First Issues : [https://goodfirstissue.dev/](https://goodfirstissue.dev/)
- Up For Grabs : [https://up-for-grabs.net/](https://up-for-grabs.net/)
- First Timers Only : [https://www.firsttimersonly.com/](https://www.firsttimersonly.com/)
- Open Source Guide : [https://opensource.guide/](https://opensource.guide/)

#### Security

- GitHub Security : [https://docs.github.com/en/code-security](https://docs.github.com/en/code-security)
- Dependabot : [https://docs.github.com/en/code-security/dependabot](https://docs.github.com/en/code-security/dependabot)

---

### Git and GitHub Glossary

| Term | Definition |
|---|---|
| **Repository** | Storage space containing all the code and history of a project |
| **Clone** | Full local copy of a remote repository |
| **Fork** | Copy of a repository on your own GitHub account |
| **Branch** | Parallel version of the code allowing work without affecting the main branch |
| **Commit** | Record of a set of changes in history |
| **Staging (index)** | Intermediate area where files are prepared before committing |
| **Push** | Sending local commits to the remote repository |
| **Pull** | Fetching and merging remote commits locally |
| **Fetch** | Fetching remote commits without merging |
| **Merge** | Merging two branches |
| **Rebase** | Rewriting history to integrate changes from another branch |
| **Pull Request (PR)** | Request to integrate a branch into another, with code review |
| **Issue** | Ticket reporting a bug, idea, or task |
| **README** | Main presentation file of a repository |
| **CONTRIBUTING** | File explaining how to contribute to the project |
| **LICENSE** | File defining the rights to use the code |
| **CI/CD** | Continuous Integration / Continuous Deployment |
| **GitHub Actions** | Automation system built into GitHub |
| **Workflow** | YAML file defining a GitHub Actions automation |
| **Tag** | Marker on a commit, often used for versions (v1.0.0) |
| **Release** | Official publication of a project version on GitHub |
| **Stash** | Temporary save of uncommitted changes |
| **Conflict** | Situation where two branches modified the same place in a file |
| **Remote** | Remote repository (as opposed to local repository) |
| **Origin** | Conventional name for the main remote (your fork or repository) |
| **Upstream** | Conventional name for the original repository when working on a fork |
| **HEAD** | Pointer indicating the current commit |
| **Gitignore** | File listing file patterns not to track with Git |
| **Semantic Versioning** | Version numbering convention : MAJOR.MINOR.PATCH |
| **Open Source** | Software whose source code is publicly available |
| **Maintainer** | Person responsible for maintaining an open source project |

---

### FAQ English

**Q : What is the difference between `git pull` and `git fetch` ?**

`git fetch` downloads new data from the remote repository but does not merge it into your local branch. `git pull` does the same but merges automatically. In practice, `git fetch` followed by `git rebase` is often preferred because it gives more control.

**Q : I made a mistake in my last commit message, how do I fix it ?**

If you have not pushed the commit yet, use `git commit --amend -m "new message"`. If you have already pushed, it is trickier because it rewrites history. It is better to create a new corrective commit in that case.

**Q : How do I undo a commit that has already been pushed ?**

Use `git revert HEAD` to create a new commit that undoes the previous one, without modifying history. This is the safe method. Avoid `git reset --hard` on commits already shared with others.

**Q : What to do when I have a conflict during a merge ?**

Git marks conflicts in files with indicators `<<<<<<<`, `=======`, `>>>>>>>`. Open the affected files, choose which version to keep (or combine both), remove the markers, then do `git add` and `git commit` to finalize the merge. Visual Studio Code has a good visual tool for resolving conflicts.

**Q : Should I commit the `node_modules/` folder ?**

No, never. The `node_modules/` folder contains dependencies and can weigh several hundred megabytes. It must be in `.gitignore`. Dependencies are reinstalled with `npm install` from the `package.json` file.

**Q : What is the difference between a fork and a clone ?**

A fork is a copy of a repository on your GitHub account (server side). A clone is a local copy on your computer. To contribute to a project you are not a collaborator on, you first fork the repository on GitHub, then clone your fork locally.

**Q : When to use `merge` vs `rebase` ?**

`merge` preserves the full history and is safer for shared branches. `rebase` rewrites history to make it more linear and readable, but should not be used on branches shared with others. For personal feature branches, `rebase` is often preferred. For merging PRs into main, both are valid depending on the project convention.

**Q : How do I know which branch is the main branch ?**

On GitHub, the main branch is indicated in the repository settings and visible on the home page. Historically named `master`, it is often renamed `main` today. On your local repository : `git branch -a` lists all branches.

**Q : How do I create a GitHub release ?**

Go to the "Releases" tab of your repository, click "Create a new release", choose or create a tag (e.g., `v1.0.0`), add a title and description, then publish.

**Q : Can I work with Git without the command line ?**

Yes. GitHub Desktop ([https://desktop.github.com/](https://desktop.github.com/)) offers a full graphical interface. Visual Studio Code also integrates a Git panel. GitKraken ([https://www.gitkraken.com/](https://www.gitkraken.com/)) is another popular option.

---

## Author

Fabien Conéjéro - [https://github.com/madjeek-web](https://github.com/madjeek-web)

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

##

##

# GitHub Projects - FAQ

---

## Q : What is this ? How does it work, explain simply ?

### What is GitHub Projects ?

It is a task management tool integrated into GitHub. Imagine a table like Notion or Trello, but directly linked to your code.

### What is it concretely used for ?

When you work on a project (alone or in a team), you have a lot of things to manage : bugs to fix, features to add, things in progress... GitHub Projects allows you to follow all of this visually without leaving GitHub.

### How does it work ?

You create "issues" (= tasks, like "fix the login bug" or "add the dark mode button"), and you organize them in a table. You can filter them (ex : see only bugs), sort them (by priority, by date...), group them (by status : To do / In progress / Done), and add custom fields (priority, deadline, responsible...).

### What you see on your screen

You have a project with 1 open issue and 0 closed. It is in Private mode (no one else can see it).

In summary : it is like a professional to-do list for your code. Very useful when your project grows and you do not want to lose track.

---

## Q : Is it private or public ?

Based on what is displayed : Private.

We can clearly see "Private" next to the project name. So only you can see it.

---

## Q : On the web, in public mode, can it also be public ?

Yes exactly ! A GitHub project can be :

- Private : only you (or your team) can see it
- Public : anyone on the internet can view it

"There aren't any projects yet" means this person has no public projects visible on their profile. Either they have not created any, or they are all set to private.

In summary : when you create a project, you choose yourself whether it is public or private.

---

## Q : What is the point of showing things there in public mode ?

To show your seriousness when you are looking for a job or an internship. A recruiter who visits your GitHub can see not only your code, but also how you organize yourself, how you manage your tasks... it looks professional.

For open source projects, if other developers contribute to your code, they can see what remains to be done, what is in progress, and organize themselves with you without having to ask you every time.

For transparency, if you develop a tool used by people, they can follow the progress, see known bugs, know what you plan to add...

In short, in private mode it is your personal draft, in public mode it is your professional showcase.

---

## Q : Same questions for : Overview, Repositories, Projects, Packages, Stars.

These are the tabs of your GitHub profile, here is what each one is used for.

### Overview

This is your main page, what people see first. You can put a presentation of yourself, your stats (commits, contributions...). It is your business card.

### Repositories

This is where all your code projects are stored. Each "repo" = one project (a website, an app, a script...). Public or private, this is where your code lives.

### Projects

We just talked about it ! These are your task management tables. Linked to your repos to organize your work.

### Packages

This is more advanced. It allows you to publish libraries or tools that other developers can install and reuse in their own projects. At your level you will probably not use it right away.

### Stars

When you find a nice project on GitHub, you can give it a star (like a "like"). This tab shows all the projects you have liked, handy for finding them later.

In summary : Repositories = your code, Projects = your organization, Stars = your favorites, Packages = what you share with the community.

---

