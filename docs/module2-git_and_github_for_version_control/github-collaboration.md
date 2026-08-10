# GitHub Collaboration

GitHub turns a local Git repository into a shared collaboration space. It adds
visibility, discussion, automation, and review around the project history.

## Core GitHub objects

When you open a repository on GitHub, a few building blocks appear repeatedly:

- **repository**: the hosted project,
- **branch**: a specific line of development,
- **issue**: a discussion or task,
- **pull request**: a proposed set of changes to review and merge,
- **Actions**: automation workflows,
- **releases**: published versions,
- **Pages**: static site hosting for documentation or project pages.

## Local repository vs. remote repository

A local repository lives on your machine. A remote repository lives on GitHub.
They are synchronized through commands such as:

```bash
git remote -v
git fetch
git pull
git push
```

The remote is often named `origin`.

## Typical collaboration path

One common GitHub-centered workflow looks like this:

1. Clone the repository.
2. Create a branch for one piece of work.
3. Commit locally.
4. Push the branch to GitHub.
5. Open a pull request.
6. Discuss and review the change.
7. Merge it.

That workflow makes each change visible and discussable before it lands on the
main branch.

## Repository settings that matter early

Some GitHub settings are worth understanding from the start:

- branch protection rules,
- repository visibility,
- collaborator permissions,
- issue templates or labels,
- GitHub Pages settings,
- large-file handling and LFS when needed.

!!! note "Screenshot placeholder"
    Add a screenshot of the main GitHub repository page showing tabs such as
    Code, Issues, Pull requests, Actions, and Settings.

## Forks vs. branches

Two collaboration patterns are common:

- **branches in the same repository** for team members who already have access,
- **forks** for outside contributors or when direct write access is not given.

For internal teaching and BAM team workflows, branches inside a shared
repository will often be the simpler starting point.

## Synchronizing with others

Before starting new work, it is good practice to update your local view:

```bash
git checkout main
git pull
```

Then create your new branch from the updated `main`.

## GitHub as project memory

GitHub is not only a place to store files. It becomes project memory:

- issues record decisions and open work,
- pull requests explain why changes happened,
- commits show the exact code history,
- release notes show what changed between versions,
- pages publish documentation for users.

That shared memory becomes especially important once a project grows beyond one
person.
