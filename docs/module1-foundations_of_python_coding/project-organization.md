# Project Organization for Small Python Projects

As soon as code grows beyond a single short script, structure starts to matter.
Good organization makes later work on testing, version control, packaging, and
collaboration much easier.

## A simple starting structure

For a small Python project, a layout like this is often enough:

```text
my-project/
├── data/
├── docs/
├── notebooks/
├── src/
│   └── my_project/
│       ├── __init__.py
│       └── analysis.py
├── tests/
├── README.md
└── pyproject.toml
```

Not every project needs every folder immediately, but the structure helps you
separate concerns.

## Useful distinctions

- Put reusable code in modules, not only in notebooks.
- Keep raw data separate from generated outputs.
- Use `tests/` for checks, even if they begin very small.
- Use `docs/` for explanations and learning material.

## Naming and modularization

Clear names reduce confusion:

- choose descriptive file names,
- group related functions into one module,
- avoid putting everything into a single giant script,
- prefer a few focused modules over one "miscellaneous" file.

## Notebooks, scripts, and packages

Each format has a role:

- **notebooks** are good for exploration and teaching,
- **scripts** are good for repeatable command-style workflows,
- **packages** are good for reusable logic shared across files or people.

A strong habit is to move stable logic out of notebooks and into Python modules.
That keeps notebooks shorter and makes the useful parts easier to test and
reuse.

## Why this matters for later modules

The topics in later RECODE modules build on this foundation:

- Git works better when changes are organized cleanly.
- AI coding assistants are more helpful in structured projects.
- Packaging becomes much easier when code already has a sensible layout.

Project organization is therefore not an "advanced extra." It is part of making
your work easier to maintain from the beginning.
