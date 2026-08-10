# Local Git Basics

This page focuses on Git on your own machine. The goal is to understand the
small set of actions that you will repeat often in real projects.

## Typical Git lifecycle

For most day-to-day work, the cycle looks like this:

1. Make changes to files.
2. Inspect what changed.
3. Stage the intended changes.
4. Commit them with a meaningful message.
5. Push them to GitHub when ready.

## Create or clone a repository

To start a new local repository:

```bash
git init
```

To copy an existing repository from GitHub:

```bash
git clone https://github.com/ORGANIZATION/REPOSITORY.git
```

Cloning is the more common workflow in collaborative environments.

## The commands you will use most

### `git status`

This is the first command to learn and the first command to trust:

```bash
git status
```

It tells you:

- which branch you are on,
- which files changed,
- which files are staged,
- whether your branch is ahead of or behind the remote.

### `git add`

Use `git add` to stage specific files for the next commit:

```bash
git add README.md
git add docs/module2-git_and_github_for_version_control/index.md
```

Staging is useful because it lets you decide what belongs together in one
commit.

### `git commit`

```bash
git commit -m "Add Module 2 handbook structure"
```

A good commit message is short, specific, and explains the main intention.

### `git log`

```bash
git log --oneline --graph --decorate
```

This helps you inspect project history in a compact way.

### `git branch` and `git switch`

```bash
git branch
git switch -c add-module2-docs
```

Use branches to keep one piece of work separate from another.

## Working tree, staging area, and history

Git is easier to understand once you separate these three states:

- **working tree**: your current edited files,
- **staging area**: the changes selected for the next commit,
- **repository history**: the commits already saved.

That mental model explains why a file can be changed but not yet staged, or
staged but not yet committed.

## Using Git in VS Code

VS Code provides a visual interface for many Git actions:

- changed files appear in the Source Control panel,
- you can stage files individually,
- diffs are shown side by side,
- commits can be created from the UI,
- branches and sync actions are visible in the status bar.

Understanding the Git concepts first makes the VS Code interface much less
mysterious.

!!! note "Screenshot placeholder"
    Add a screenshot of the VS Code Source Control panel showing changed files,
    staged files, and the commit box.

## Good commit habits

- Keep commits focused on one idea.
- Do not mix unrelated cleanup with a functional change.
- Commit often enough to create meaningful checkpoints.
- Write messages that help your future self.

## A useful first command set

For a typical documentation change:

```bash
git status
git switch -c improve-module2-docs
git add docs/module2-git_and_github_for_version_control/
git commit -m "Add Module 2 handbook pages"
git push -u origin improve-module2-docs
```

## What comes next

After the local basics, the next step is understanding how repositories live on
GitHub, how remotes work, and how collaboration happens around the hosted
repository.
