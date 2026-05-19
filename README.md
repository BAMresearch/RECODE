# **RECODE** (Crash Course on **RE**search **CO**ding and **DE**velopment)

RECODE is a project-oriented course designed to train BAM researchers with
practical skills in scientific software development. It bridges the gap
between day-to-day research work and modern software development practice by
focusing on code that is clear, reproducible, maintainable, and reusable.

The course combines Python programming fundamentals with tools and workflows
that help participants design, build, document, and share research software.
By the end of the course, participants should feel more confident structuring
their code professionally, using version control, working with modern AI coding
assistants, and packaging their work for others.

## Course contents

- [Module 1 - Foundations of Python Coding](docs/module1-foundations_of_python_coding/index.md)
- [Module 2 - Git and GitHub for Version Control](docs/module2-git_and_github_for_version_control/index.md)
- [Module 3 - Using Large Language Models (LLMs) for Coding Assistance](docs/module3-using_large_language_models_for_coding_assistance/index.md)
- [Module 4 - Packaging and Distributing Python Projects](docs/module4-packaging_and_distributing_python_projects/index.md)
- Module 5 - Productive Development Environment

## Learning approach

RECODE follows a hands-on and project-oriented approach. Participants are
encouraged to bring their laptops and, ideally, a real project or idea they
would like to develop during the course. For those without a project, example
topics based on open-source resources can be provided.

We structure the course as follows:

- The course is divided into **modules**, each centered on one software
  development topic.
- Each module is divided into **sections** with short theory, live examples,
  hands-on exercises, and optional quizzes.
- Modules are presented in **sessions** of roughly 1.5 to 2 hours, typically
  one session per week.
- After each module, participants should have time to work on their own
  projects with support from trainers and peers.

RECODE is intended as a repeatable training format that can evolve over time
and support continuous learning at BAM.

## Technical requirements

Participants are expected to use Visual Studio Code (VS Code) as their primary
Integrated Development Environment (IDE). Basic usage of the interface
(opening folders, running scripts, using the integrated terminal) will be
covered early in the course, while more advanced features are introduced later.
VS Code is available through the BAM Software Portal.

Participants are also asked to install Miniforge3. Setup guidance for standard
BAM laptop configurations is included in the course material.

Participants are encouraged to create a GitHub account and share their username
with the course organizers:

- [Jose M. Pizarro](https://github.com/JosePizarro3/)
- [Simon Müller](https://github.com/dudelguy)
- [Ingo Breßler](https://github.com/ibresslerBAM)

Participants can then be invited to the BAMResearch GitHub organization to
store projects and practice version control workflows during the course.

## Future expansion

The RECODE modules are designed to grow over time. Future additions could
include topics such as _working with Linux environments_,
_Docker containerization_, or _scientific instrumentation software
development_, allowing BAM researchers to deepen their software development
expertise step by step.

## Developing the documentation locally

The documentation site is built with **Zensical** and configured through
[`zensical.toml`](zensical.toml). The source pages live in [`docs/`](docs/).

### Prerequisites

- Python 3.12
- [`uv`](https://docs.astral.sh/uv/)

### Install development dependencies

```bash
uv sync --dev
```

### Start a local preview server

Run:

```bash
uv run zensical serve
```

or directly:

```bash
zensical serve
```

Zensical will print a local URL in the terminal. Open that address in your
browser to preview the site while editing pages in `docs/`.

### Build the static site

```bash
uv run zensical build
```

Use the build command before publishing or when you want to confirm that the
navigation and Markdown pages render cleanly.

