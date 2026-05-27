# Getting Ready: Python Environment and Tools

Before writing code, you need a setup that is predictable and easy to use.
This module assumes that participants work with:

- **VS Code** as the main editor,
- **Miniforge** to manage Python environments,
- **Jupyter Notebooks** for interactive exercises,
- a **terminal** for running commands explicitly.

## Why this setup matters

A good environment helps you avoid several common beginner problems:

- using the wrong Python installation,
- mixing project dependencies together,
- not knowing where packages were installed,
- running code in one tool but editing another.

The goal is not to memorize every tool immediately. The goal is to create a
setup you can trust.

## Installation checklist

For a standard BAM setup, make sure you have:

1. **Miniforge** installed for your user account.
2. **VS Code** installed, with additional extensions (which install more extensions they depend on, 9 in sum):
    - Python extension by Microsoft
    - Jupyter extension by Microsoft
4. A **GitHub account** ready for the course.

If BAM-specific installers are distributed through the software portal, prefer
those versions unless the course team recommends otherwise.

## Create a dedicated Python environment

Using one environment per project or purpose is a healthy default. There are mainly two options:

### venv

A virtual environment `venv` which is purely Python-based. It comes as a module in each Python installation and it can manage multiple environments (in local folders) with an independet set of packages in each. But they are bound to the Python version, venv is running with. This is the minimal and fast variant.

  ```bash
  python -m venv .venv
  source .venv/bin/activate
  ```

### Conda

A `conda` environment, managed by **MiniForge**. It has the benefit to manage more than just Python packages. It can install system application with binaries (non-Python based) as well and it lets you install different Python versions in each environment which is great when dealing with older code or apps.

For this course, Miniforge and `conda` are a practical starting point. You create a Jupyter-focused environment like this:

```bash
conda create --name jlab python=3.12
conda activate jlab
conda install jupyterlab notebook numpy scipy pandas matplotlib openpyxl lmfit
```

## Configure VS Code

After installation:

1. Open VS Code.
2. Install the **Python** extension from Microsoft.
3. Open your working folder.
4. Select the Python interpreter from your Miniforge environment.

Once the interpreter is selected correctly, the terminal, script runner, and
notebook support in VS Code will all become much more consistent.

## Start using Jupyter Notebooks

Notebooks are useful when you want to:

- experiment with code step by step,
- mix explanation and code in one place,
- show results such as tables or plots immediately,
- teach interactively during a live session.

They are excellent for exploration, but not always the best final form for
production code. A useful rule of thumb is:

- use notebooks to explore, explain, and prototype,
- move stable logic into scripts or modules once it starts to grow.

## Verify that your setup works

These checks should succeed:

```bash
python --version
conda --version
jupyter lab --version
```

Inside Python, you should also be able to import common scientific packages:

```python
import numpy
import pandas
import matplotlib
```

If all of that works, your environment is ready for the rest of Module 1.

## Common troubleshooting ideas

- If VS Code runs the wrong interpreter, re-select it from the command palette.
- If a package import fails, check whether the correct environment is active.
- If a notebook kernel is missing, make sure Jupyter is installed in the same
  environment you selected in VS Code.
- If installation asks for admin rights unexpectedly, verify whether a
  user-level installation is possible before escalating.

## What comes next

Once your tools are working, the next step is learning how Python code is
structured: expressions, variables, types, functions, and simple programs.
