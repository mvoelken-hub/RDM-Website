---
description: Why version control matters, core Git workflows, and .gitignore for research data.
---

# 3. Version Control with Git

The manual versioning introduced in Module 2, incrementing a number in a filename, works for a handful of revisions but becomes unwieldy once a file changes frequently or several people edit it in parallel. Git is a version control system designed for exactly this situation. This module introduces why version control matters, the core concepts Git is built on, and the everyday commands used to track changes locally and share them with others.

!!! tip "In this module"
    - Why version control matters, and how Git differs from centralized systems
    - Core local Git workflows: init, add, commit, log, diff, branch
    - Working with remote repositories and .gitignore for research data

## Introduction to Git

### Why Version Control

A version control system records every change made to a file in a traceable way, including who made it and when. It allows a return to any earlier state without duplicating files by hand, unlike the manual versioning approach from Module 2. In research, this is particularly valuable for code, analysis scripts, and structured data. It is less well suited to very large volumes of raw data, a limitation discussed further below.

### Git vs. Other Version Control Systems

Git was created in 2005 by Linus Torvalds and is free and open source. Unlike older, centralized systems such as SVN or CVS, Git is distributed: every contributor holds a complete local copy of the repository's history, not just a snapshot of the current state. Git therefore continues to work offline and is more resilient to the failure of a central server than a centralized system would be.

### Installation and Configuration

Git runs across Windows, macOS, and Linux, and on Windows is commonly used through Git Bash. After installation, the basic configuration step is to set a name and email address, since both are recorded in every commit made afterward. Graphical interfaces, such as GitHub Desktop or GitKraken, are a useful complement to the command line for anyone starting out.

### Core Concepts: Repositories, Commits, Branches

A repository is the project folder managed by Git, together with its complete history of changes. A commit is a saved snapshot of the current state of the files, together with a description of what changed and why. A branch is a parallel line of development, used to work on a feature or an experiment without affecting the main line of work.

## Git Basics (Local)

### Initializing a Repository

The command `git init` turns an existing folder into a local Git repository. Alternatively, an existing repository can be downloaded with `git clone`, covered under remote repositories below.

### Tracking Changes

`git add` marks changed files for the next commit, a step known as staging. `git commit` then saves the staged changes permanently to the history, together with a commit message.

### Viewing History

`git log` lists every commit together with its author, date, and message. `git diff` shows the specific line-by-line changes between two states, the current working state against the most recent commit, for instance.

### Branches

Branches allow parallel work on a feature or an experiment without putting the main code or dataset at risk. Once the work is complete, a branch is merged back into the main line with `git merge`.

### .gitignore for Research Data

A `.gitignore` file specifies which files or folders Git should not track. This is useful for automatically generated files, such as build artifacts and caches, and, as a rule, for large raw data files and sensitive files such as `.env` files or credentials, none of which belong in the repository itself. Research data specifically often needs its own strategy here: large or binary files are usually better managed through a dedicated repository, covered in Module 7, or through Git LFS, rather than committed to Git directly.

## Remote Repositories

### Clone, Pull, Push

`git clone` copies an entire remote repository, one hosted on GitHub or GitLab for instance, to a local machine, including its full history. `git pull` retrieves new changes from the remote repository and merges them with the local state. `git push` transfers local commits to the remote repository.

### Handling Conflicts

A conflict arises when the same part of a file has been changed differently, both locally and on the remote. Git marks the affected sections directly within the file content. The conflict must then be resolved by hand before the merge can complete.

### Commit Message Best Practices

A good commit message keeps its subject line short, around fifty characters as a rough guide, capitalized, and without a trailing period. The imperative mood is preferred: "Add", "Fix", or "Update" rather than "Added", "Fixed", or "Updated". A blank line separates the subject from a longer description, which should explain what changed and why rather than how. Committing in small, complete steps, after each finished sub-task, is preferable to a single large commit gathering an entire day's work at the end.

### Git for Different Data Types

Git is well suited to code, text, and structured configuration files, since line-by-line diffs and merges work reliably for them. It is poorly suited to large binary research data, such as raw measurement dumps or images: the repository grows without bound, and diffs carry no meaningful information for these formats. The common solution is to keep code and analysis scripts in Git while placing raw data in a dedicated data repository, covered in Module 7, linked back to the code through persistent identifiers rather than duplicated as files inside the Git repository itself.

## Worked Example

Consider a small Python script that processes the BET and XRD measurements from the nickel-catalyst example introduced in Module 1. A first commit, `git init` followed by `git add analyze_bet.py` and `git commit -m "Add initial BET analysis script"`, establishes the starting point. As the script is extended to also parse XRD peak positions, a second commit, `git commit -m "Add XRD peak fitting"`, records that specific change on its own rather than bundling it with unrelated edits. The raw instrument files that `analyze_bet.py` reads are excluded from the repository through a `.gitignore` entry such as `raw/*.xlsx`, since they belong in the folder structure from Module 2 and, eventually, in a data repository, not in the Git history of the analysis code.

## Step-by-Step Guide: Initializing a Repository and Making a First Commit

1. Install Git and set a name and email address as a one-time configuration step.
2. Open a terminal in the project folder and run `git init`.
3. Create a `.gitignore` file listing any large data files or sensitive files that should not be tracked.
4. Stage the files to be tracked with `git add <filename>`, or `git add .` to stage everything not excluded by `.gitignore`.
5. Record the first commit with `git commit -m "Initial commit"`.
6. Run `git log` to confirm the commit was recorded.

## Self-Check

??? question "1. What makes Git a distributed version control system, unlike SVN or CVS?"
    Every contributor holds a complete local copy of the repository's history, not just a snapshot of the current state, so Git continues to work offline and does not depend on a central server being available.

??? question "2. What is the difference between git add and git commit?"
    git add stages changed files for the next commit. git commit then saves the staged changes permanently to the history, together with a commit message.

??? question "3. Why is Git poorly suited to large raw research datasets?"
    The repository grows without bound as large binary files accumulate, and diffs between versions of such files carry no meaningful information, unlike line-by-line diffs for code or text.

??? question "4. What should a .gitignore file typically exclude in a research project?"
    Automatically generated files such as build artifacts and caches, sensitive files such as credentials, and, generally, large raw data files that are better managed through a dedicated data repository.

## Next Steps

- Continue to [Module 4: Collaboration with GitHub & GitLab](../04-collaboration/index.md), which builds on local Git with shared, remote workflows.
- Further reading: the [Atlassian Git tutorial](https://www.atlassian.com/git) and the [GitKraken commit message guide](https://gitkraken.com/learn/git/best-practices/git-commit-message).
