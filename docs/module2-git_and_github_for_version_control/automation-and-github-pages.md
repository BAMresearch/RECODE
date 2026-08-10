# Automation and GitHub Pages

Once a repository is under version control, GitHub can do more than store code.
It can also run checks and publish documentation automatically.

## Why automation matters

Automation reduces repetitive manual work and catches problems earlier.
Examples include:

- running tests on each pull request,
- checking formatting or linting,
- building documentation,
- deploying a project site or docs site,
- validating that files are complete and consistent.

## GitHub Actions

GitHub Actions is GitHub's workflow automation system. Workflows are usually
stored in:

```text
.github/workflows/
```

A workflow can react to events such as:

- a push to a branch,
- a pull request,
- a manual trigger,
- a release creation.

!!! note "Screenshot placeholder"
    Add a screenshot of the GitHub Actions tab showing workflow runs and their
    success or failure states.

## What checks should beginners care about first?

For a course project or small scientific software project, a lightweight first
set of checks is often enough:

- tests,
- linting or formatting,
- documentation build validation.

The goal is not maximum automation immediately. The goal is to protect the
important basics.

## `.gitignore`

One of the most practical Git skills is ignoring files that should not be
tracked, such as:

- temporary files,
- virtual environments,
- build outputs,
- editor-specific folders,
- secrets or local configuration files.

Example:

```gitignore
.venv/
__pycache__/
.DS_Store
.vscode/
dist/
site/
```

The exact entries depend on the project, but learning to separate source files
from generated or local-only files is essential.

## Pre-commit hooks

Pre-commit hooks let you run checks automatically before a commit is created.
They are useful for tasks such as:

- formatting code,
- trimming trailing whitespace,
- checking YAML or Markdown syntax,
- preventing obviously bad commits.

In teaching, they are a good example of how teams encode quality rules into the
workflow itself.

## Secrets

Some automation needs credentials, such as deployment tokens or API keys.
These should never be committed directly into the repository.

GitHub provides repository and organization secrets for this purpose.

!!! warning
    Secrets should be treated carefully. In a training module, it is usually
    enough to explain the concept and show where secrets are configured, rather
    than exposing real credentials.

## GitHub Pages

GitHub Pages is a static site hosting feature that can publish:

- project documentation,
- course material,
- simple websites,
- landing pages for repositories.

For RECODE participants, this is especially useful because it gives a clear
example of how a documentation repository becomes a published website.

## Typical GitHub Pages flow

1. Keep docs source files in the repository.
2. Use a workflow to build the site.
3. Publish the generated output through GitHub Pages.
4. Rebuild the site when relevant content changes.

!!! note "Screenshot placeholder"
    Add a screenshot of the repository Settings page showing the GitHub Pages
    configuration section.

## Why this matters for the course

GitHub Pages makes version control feel concrete for beginners:

- a branch changes,
- a workflow runs,
- a site updates,
- the documentation becomes visible to others.

That connection between repository, automation, and published result is one of
the most motivating parts of the module.
