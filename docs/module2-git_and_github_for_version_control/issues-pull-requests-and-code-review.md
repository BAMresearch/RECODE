# Issues, Pull Requests, and Code Review

This page focuses on the collaboration features that matter most for team
development on GitHub.

## Issues

Issues are lightweight work items or discussion threads. They are useful for:

- reporting bugs,
- proposing features,
- tracking documentation tasks,
- collecting follow-up work,
- organizing module or project planning.

Good issues usually include:

- a short descriptive title,
- a short explanation of the problem or goal,
- context or screenshots when relevant,
- clear next steps or acceptance criteria if known.

!!! note "Screenshot placeholder"
    Add a screenshot of a GitHub Issues page showing labels, assignees, and an
    example issue body.

## Pull requests

A pull request, often shortened to **PR**, proposes a set of changes from one
branch into another branch.

A PR is useful because it creates a place to:

- summarize the change,
- discuss decisions,
- request review,
- run automated checks,
- merge only after the work is ready.

## A healthy PR workflow

1. Create a branch for one change.
2. Push the branch to GitHub.
3. Open a pull request into `main`.
4. Describe what changed and why.
5. Request review when appropriate.
6. Address comments and update the branch.
7. Merge after approval and passing checks.

## Writing a good PR description

A strong PR description often answers:

- What problem does this solve?
- What files or behavior changed?
- How should someone review it?
- Are there follow-up tasks?

For UI or documentation work, screenshots can be very helpful.

!!! note "Screenshot placeholder"
    Add a screenshot of a pull request page showing the description, changed
    files tab, review request area, and status checks.

## Code review mindset

Review is not only about finding mistakes. It is also about:

- checking clarity,
- protecting maintainability,
- catching risky changes early,
- sharing knowledge across the team.

Helpful review comments are specific, respectful, and actionable.

## Merge conflicts

Conflicts happen when Git cannot combine two lines of work automatically.
This is normal, not a sign that something went badly wrong.

A common approach is:

```bash
git checkout main
git pull
git checkout your-branch
git merge main
```

Or, if the team prefers it, rebase instead of merge. The important beginner
lesson is to understand the conflict, edit carefully, and test afterwards.

## Linking issues and pull requests

GitHub can connect PRs and issues directly. For example, writing:

```text
Closes #12
```

in the PR description will close issue `#12` automatically when the PR is
merged.

This is a simple but powerful way to keep planning and implementation connected.
