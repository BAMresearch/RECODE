# Getting Ready: Python Environment and Tools

Before writing code, you need a setup that is predictable and easy to use.
This module assumes that participants work with:

- **VSCode** as the main editor (IDE),
- **Miniforge** to manage Python environments,
- **Jupyter Notebooks** for interactive exercises,
- a **terminal** for running commands explicitly.

## Why this setup matters

A good environment helps you avoid several common beginner problems:

- using the wrong Python installation,
- mixing project dependencies together,
- not knowing where packages were installed,
- running code in one tool but editing another.

In general, knowing how to create a good setup:

- enhances reproducibility,
- changes/package installations do not influence main Python installation, and
- if something breaks, you do not have to reinstall everything, just recreate the virtual environment.

The goal is not to memorize every tool immediately. The goal is to create a setup you can trust.

## Installation checklist

For a standard BAM setup, make sure you have:

1. **Miniforge** installed for your user account.
2. **VSCode** installed, with additional extensions (which install more extensions they depend on):
    - [Python extension by Microsoft](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
    - [Jupyter extension by Microsoft](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter)
3. A **GitHub account** ready for the course.

If BAM-specific installers are distributed through the software portal, prefer those versions unless the course team recommends otherwise.

## Create a dedicated Python environment

Virtual environments are used to handle coding projects individually by separating specific package installations from the core operating system. This is done to avoid cluttering or clashing different packages versions in your core system. Using one environment per project or purpose is a healthy default and key for reproducibility of software. There are mainly two options: `venv` and `conda`.

### venv

A virtual environment `venv` is used when your work is purely Python-based. It comes as a module in each Python installation and it can manage multiple environments separated in local folders, each with an independet set of packages. But they are bound to the Python version is running with. This is the minimalistic and fastest variant.

In Ubuntu:

```bash
python -m venv .venv
source .venv/bin/activate
```

### Conda

A `conda` environment managed by Miniforge has the benefit to manage more than just Python packages. It can install system application with binaries (non-Python based) as well and it lets you install different Python versions in each environment which is great when dealing with older code or apps. In comparison with `venv`, `conda` is slower and more focused on larger, more complex scientific applications which require cross-language programming.

For this course, Miniforge and `conda` are a practical starting point. Open a command line interface (`powershell`/`cmd` in Windows, or a terminal in Ubuntu). In VSCode, you should click in *Terminal > New Terminal* on the top right menu (see below). You should see a bottom window with:

```bash
Microsoft Windows [Version 10.0.26200.9168]
(c) Microsoft Corporation. All rights reserved.

C:<path to your directory when new terminal is opened>
```

You can create a Jupyter-focused environment as;

```bash
conda create --name jlab python=3.12
```

Miniforge will start the installation and prompt you to confirm by typing `y` in the terminal. Go ahead and let the process finish. When the process finished, you can activate your newly created environment as:

```bash
conda activate jlab
```

And install specific packages by using `conda install <package name>`. In this Module, we will need to install:

```bash
conda install jupyterlab notebook numpy scipy pandas matplotlib openpyxl lmfit
```

## VSCode as our IDE

Integrated Development Environments (IDEs) are tools that are key to perform software development activities. They are very good to manage projects and code, as well as for providing extensions useful during the development process.

You can also write Python code in every sinple text editor (Notepad, Notepad++, vim, Kate, ...), but an IDE will help you with:

- Extensions designed for writing code
- Nice formatting
- Easy usability
- A lot of automatic integrations and assisting functions
- Code/Project management

Visual Studio Code (VSCode) is an IDE developed by Microsoft, available for Windows, Linux and macOS. It is widely used and available in BAMs Software Portal and it will be the only IDE used throughout the course. If you are already using another one, that is fine, you can continue with that, as an IDE is simply a tool to visualize and operate code.

<div class="click-zoom">
    <label>
        <input type="checkbox">
        <img src="https://github.com/user-attachments/assets/52e9c33e-99dd-494c-97ec-ae809007f192" alt="Login in the Parser App." width="80%" title="Click to zoom in">
    </label>
</div>

### Configure VSCode

After installation:

1. Open VSCode.
2. Make sure, at least the **Python** extension from Microsoft is installed.
3. Open your working folder, or create a new one.
4. Select the Python interpreter from your Miniforge environment created above.

Once the interpreter is selected correctly, the terminal, script runner, and notebook support in VSCode will all become much more consistent.

<div class="click-zoom">
    <label>
        <input type="checkbox">
        <img src="https://github.com/user-attachments/assets/e867191b-ae4a-4906-9def-8911a9dacd94" alt="Login in the Parser App." width="80%" title="Click to zoom in">
    </label>
</div>

## Start using Jupyter Notebooks

Jupyter Notebooks are an interactive computing environment used mainly for data analysis, scientific computing, and coding education. They let you write code, run it, and see the results — all in one document. A Jupyter Notebook combines three things in a single file:

* **Code** (usually Python, but also R, Julia, etc.)
* **Text explanations** (formatted with Markdown)
* **Output** (charts, tables, images, printed results)

This makes them extremely useful for explaining your work step by step. A notebook is made up of **cells**:

* **Code cells** → where you write and run code
* **Markdown cells** → where you write text, notes, or explanations

When you run a code cell, the output appears directly below it.

### Example

A simple Python example in a notebook:

```python
x = 5
y = 3
x + y
```

Output:

```
8
```

You can immediately see the result without needing a separate output window.

Notebooks are saved as `.ipynb`. This file contains all code, text, and outputs.

### When to use Notebooks

They are useful when you want to:

- experiment with code step by step,
- mix explanation and code in one place,
- show results such as tables or plots immediately,
- teach interactively during a live session.

They are excellent for exploration, but not always the best final form for production code. A useful rule of thumb is:

- use notebooks to explore, explain, and prototype,
- move stable logic into scripts or modules (Python files with `.py` extension) once it starts to grow.

## Verify that your setup works

Inside a Jupyter Notebook or Python file, you should also be able to import common scientific packages:

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

- If VSCode runs the wrong interpreter, re-select it from the command palette.
- If a package import fails, check whether the correct environment is active.
- If a notebook kernel is missing, make sure Jupyter is installed in the same environment you selected in VSCode.
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
