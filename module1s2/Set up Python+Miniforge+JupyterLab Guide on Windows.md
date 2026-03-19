# Python+Miniforge+JupyterLab Install and Update Guide for Windows

- For a unprivileged user, without administrative rights
- If a window, asking for an (admin) password pops up during installation or when installing any packages, just ignore it by closing the window. The installers should switch to user-mode then.

## Install

1. Search for Miniforge in the Internetz or download from here directly: https://conda-forge.org/miniforge/
2. Install Miniforge for the current user only
3. Create a dedicated environment for Jupyter Lab:

        conda create --name jlab

    Or with a specific Python version

        conda create --name jlab --solver libmamba python=3.12.*
    
    And activate it:
    
        conda activate jlab
    
4. Install further packages, such as [Jupyter Lab][1], Pandas and more:

        conda install jupyterlab notebook numpy scipy pandas openpyxl lmfit

5. Install *nbopen* via *pip* because it is not available in the *conda-forge* channel:

        pip install nbopen jupyter-analysis-tools
    
    Install the Windows App association for Jupyter Notebooks so that they open once double-clicked:
    
        python -m nbopen.install_win

[1]: https://jupyterlab.readthedocs.io/en/stable/getting_started/overview.html

## Update

Open *Miniforge Prompt* in environment *(base)* and enter the command:

    conda update --all -c conda-forge

After a while a list of packages to update appears. Accept and proceed by typing `y` followed by pressing the *Enter* key.

**Note**: The same applies for other environments. For the *jlab* environment created above, you need to activate that first by `conda activate jlab` and then updating all packages by the command given here: `conda update --all -c conda-forge`.

## GIT for version control

For download and install GIT from https://git-scm.com/install/.

## MS Visual Code Editor

1. Install MS VS Code from https://code.visualstudio.com

2. Extensions Menu (icon with 4 squares on left sidebar): Install the 'Python' extension by Microsoft
    - In the start page of this extension 'Get Started with Python Development', either 'Create Environment' for completely new installations or
    - 'Select Python Interpreter' by pointing it to the directory where miniforge was installed to and an environment which might exist already therein. It should offer the detected environment for selection in the top most bar of the VS Code Window.
