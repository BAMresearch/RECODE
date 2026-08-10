# Common Mistakes and Safe Recovery

Git feels much less intimidating once you learn that most mistakes are
recoverable. This page focuses on calm, safe actions for common situations.

## General rule

Before trying to "fix everything," start with:

```bash
git status
git log --oneline --graph --decorate -10
```

Those two commands tell you where you are and what recently happened.

## I changed a file but did not commit yet

Inspect the change first:

```bash
git diff
```

If the change is useful, stage and commit it. If it was accidental, decide
carefully whether you want to discard it.

## I committed on the wrong branch

If the commit is still only local, you can often create a new branch from the
current state and continue there:

```bash
git switch -c correct-branch-name
```

That is often safer for beginners than trying to rewrite history immediately.

## My branch is behind `main`

Update your main branch first, then bring those changes into your branch:

```bash
git checkout main
git pull
git checkout your-branch
git merge main
```

If the team prefers rebasing, use that workflow consistently, but do not mix
strategies randomly.

## I have a merge conflict

Conflicts mean Git needs your help deciding which changes to keep.
The basic flow is:

1. Open the conflicted files.
2. Read both sides carefully.
3. Edit the file into the intended final version.
4. Stage the resolved file.
5. Complete the merge or rebase step.

Afterwards, test or preview the result if possible.

## I pushed something and now realize it was incomplete

The simplest recovery is usually to make a follow-up commit that corrects the
problem. That keeps history honest and avoids more advanced recovery steps.

For a course module, that is a good default:

- prefer additive fixes,
- prefer small corrective commits,
- avoid history rewriting unless you understand the consequences.

## I accidentally tracked files that should be ignored

First update `.gitignore`, then remove the files from Git tracking while
keeping them locally if needed. This is a common beginner issue with:

- virtual environments,
- notebook checkpoints,
- generated build outputs,
- editor folders.

## When to ask for help

Ask for help early if:

- you are unsure whether a command rewrites history,
- the branch has already been shared with others,
- a conflict touches many files,
- a secret may have been committed,
- you are tempted to run a command you do not understand.

## The most important beginner lesson

Git is not about never making mistakes. It is about making mistakes in a system
that records enough history for recovery and collaboration.
