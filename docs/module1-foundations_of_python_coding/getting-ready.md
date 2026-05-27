# Getting Ready: Python Environment and Tools

Before writing code, you need a setup that is predictable and easy to use.
This module assumes that participants work with:

- **VS Code** as the main editor (IDE),
- **Miniforge** to manage Python environments,
- **Jupyter Notebooks** for interactive exercises,
- a **terminal** for running commands explicitly.

## Why this setup matters

A good environment helps you avoid several common beginner problems:

- using the wrong Python installation,
- mixing project dependencies together,
- not knowing where packages were installed,
- running code in one tool but editing another.

In general:

- Enhance reproducability
- Changes/package installations do not influence main Python installation
- If something breaks, you do not have to reinstall everything, just recreate the virtual environment

The goal is not to memorize every tool immediately. The goal is to create a setup you can trust.

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

Virtual environments are used to handle coding projects individually.
Using one environment per project or purpose is a healthy default.
There are mainly two options:

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

## On IDEs (What & Why)

- Basically, you can write Python code in every sinple text editor (Notepad, Notepad++, vim, Kate, ...)
- Using „Integrated Development Environments“ (IDEs) is often preferred:
    - Software designed for writing code
    - Nice formatting
    - Easy usability
    - A lot of automatic integrations, assistence functions
- Visual Studio Code (VSCode) is an IDE developed by Microsoft
- It is available for Windows, Linux and macOS
- It is widely used and available in BAMs Software Portal

<img width="1499" height="806" alt="image" src="https://github.com/user-attachments/assets/52e9c33e-99dd-494c-97ec-ae809007f192" />



## Configure VS Code

After installation:

1. Open VS Code.
2. Make sure, at least the **Python** extension from Microsoft is installed.
3. Open your working folder, or create a new one.
4. Select the Python interpreter from your Miniforge environment created above.

Once the interpreter is selected correctly, the terminal, script runner, and
notebook support in VS Code will all become much more consistent.

<img width="1499" height="841" alt="image" src="https://github.com/user-attachments/assets/e867191b-ae4a-4906-9def-8911a9dacd94" />

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

Inside a Python file (as shown in the screenshot above), you should also be able to import common scientific packages:

```python
import numpy
import pandas
import matplotlib
```

If all of that works, your environment is ready for the rest of Module 1.

## Common troubleshooting

These checks should succeed in the terminal of VSCode:

```bash
python --version
conda --version
jupyter lab --version
```

- If VS Code runs the wrong interpreter, re-select it from the command palette.
- If a package import fails, check whether the correct environment is active.
- If a notebook kernel is missing, make sure Jupyter is installed in the same
  environment you selected in VS Code.
- If installation asks for admin rights unexpectedly, verify whether a
  user-level installation is possible before escalating.

### Execution Policy Error

In Powershell or Windows Terminal or VSCode Terminal, you may get the error `File C:\Users\tom\Documents\WindowsPowerShell\profile.ps1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https:/go.microsoft.com/fwlink/?LinkID=135170.`

That error means Windows PowerShell's execution policy prevents running profile scripts (needed by Conda/MiniForge too). The recommended solution is to allow scripts for the current user only:
```
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned -Force
```
`RemoteSigned` here lets locally created scripts run, downloaded scripts must be signed.

Verify to confirm the policy for the relevant scope is RemoteSigned (or Bypass for Process):
```
Get-ExecutionPolicy -List
```

## What comes next

Once your tools are working, the next step is learning how Python code is
structured: expressions, variables, types, functions, and simple programs.
