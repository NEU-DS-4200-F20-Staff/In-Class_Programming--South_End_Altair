# In-Class Programming — South End Altair

~*25 min total*

This repository is your starting point for the tutorial and includes instructions below.

# Aim of the tutorial

[Altair](https://altair-viz.github.io/) is a declarative statistical visualization library for Python, based on [Vega](http://vega.github.io/vega) and [Vega-Lite](http://vega.github.io/vega-lite).
In this tutorial you will learn how to use Jupyter Lab and Altair.

# Instructions

## Setup instructions

1. Clone the repo.
1. `CD` to the repo directory. Create and activate a virtual environment for this project. You may need to modify the code you use depending on what Python you have installed and how your machine is configured.
  * On macOS or Linux:
    ```
    python3 -m venv env
    source env/bin/activate
    which python
    ```
  * On Windows:
    ```
    python -m venv env
    .\env\Scripts\activate.bat
    where python
    ```
1. Install necessary packages. Note that you should install the exact versions of the packages.
    ```
    pip install -r requirements.txt
    ```
    This may take a few minutes.

## Run Jupyter Lab and create a notebook

1. Run `jupyter lab`. It should open Jupyter Lab in your default browser.
1. Create a new Jupyter Notebook .ipynb file and give it a descriptive title.
1. Follow along with the in-class tutorial. If you get lost, you can look at `south_end_complete.ipynb`.

Once you have written code in a cell you can run it with `ctrl+enter`. In the menu you can run all cells and restart the kernel to clear variables.

## When we are done with the tutorial...
Start working through the [Altair data visualization curriculum](https://github.com/uwdata/visualization-curriculum).

## At the end of the exercise...

### Quit Jupyter Lab and the virtual environment
1. Make sure to save your .ipynb file and shutdown Jupyter Lab properly through the file menu. Otherwise you need to use `jupyter notebook stop`.
1. Deactivate the venv to return to your terminal using `deactivate`.

## Commit and push your code (but first...)

1. If you have made any changes to the required packages you should export a list of all installed packages and their versions:
   ```
   pip freeze > requirements.txt
   ```

1. **Before you commit a Jupyter Notebook .ipynb file, clear the outputs of all cells.** This decreases file size, removes unnecessary metadata, and makes diffs easier to understand. In Jupyter Lab you can use the GUI: Edit->Clear All Outputs.

1. Make sure to add all your required files, including the .ipynb file and any images.

1. Finally, commit all your local code and push it to your remote GitHub Classroom-generated repository.

# Submission instructions

* Submit the link to your GitHub repository on Canvas.

# Additional Resources

Check the [Altair documentation](https://altair-viz.github.io/). Feel free to take inspiration from the [Altair example gallery](https://altair-viz.github.io/gallery/index.html).


## Optional git setup to automatically clear metadata using JQ (Highly Recommended)

1. Install JQ by running, e.g., `sudo apt-get install jq`. For more options including your operating system check [the JQ download site](https://stedolan.github.io/jq/download/).
2. Append the following block of code either in your local repo `.gitconfig` file or your global `.gitconfig`. I would recommend to do it in your global `.gitconfig` so you don't need to redo that for future .ipynb files.<br>
    ```
    [core]
    attributesfile = ~/.gitattributes_global
    [filter "nbstrip_full"]
    clean = "jq --indent 1 \
            '(.cells[] | select(has(\"outputs\")) | .outputs) = []  \
            | (.cells[] | select(has(\"execution_count\")) | .execution_count) = null  \
            | .metadata = {\"language_info\": {\"name\": \"python\", \"pygments_lexer\": \"ipython3\"}} \
            | .cells[].metadata = {} \
            '"
    smudge = cat
    required = true
    ```
    For more details look at this great tutorial [here](http://timstaley.co.uk/posts/making-git-and-jupyter-notebooks-play-nice/).
    You can use this command `git config --list --show-origin --show-scope` to find out where your git configuration is stored.
3. Create a global gitattributes named `.gitattributes_global` file (usually placed at the root level, so `~/.gitattributes_global`).
4.  Add the following line of code:
    ```
    *.ipynb filter=nbstrip_full
    ```

## Optional features

* To get markdown section numbering use [jupyterlab-toc](https://github.com/jupyterlab/jupyterlab-toc).
  * To install run: `jupyter labextension install @jupyterlab/toc`
  * Then click the enumerated list button on the left strip in JupyterLab to bring up the table of contents. There you can click the itemized list button in the top to add section numbers to the markdown cells.
​
* There is also a useful [Spellchecker](https://github.com/ijmbarr/jupyterlab_spellchecker) extension.
  *  To install run: `jupyter labextension install @ijmbarr/jupyterlab_spellchecker`

​* To install both of the above run: `jupyter labextension install @jupyterlab/toc @ijmbarr/jupyterlab_spellchecker`

## Troubleshooting

* For Altair problems, see [the UW Visualization Curriculum debugging guide](https://github.com/uwdata/visualization-curriculum/blob/master/altair_debugging.ipynb) and [the Altair FAQ](https://altair-viz.github.io/user_guide/faq.html).

* Googling error messages can also help you sort out weird issues with Python and Jupyter Lab.

* If you get a `NotImplementedError` for `asyncio` while running Python 3.8,
edit `/env/Lib/site-packages/tornado/platform/asyncio.py` following the instructions [here](https://stackoverflow.com/questions/58422817/jupyter-notebook-with-python-3-8-notimplementederror/). Right after the line `import asyncio` add these lines:
    ```
    import sys
    if sys.platform == 'win32':
        asyncio.set_event_loop_policy(asyncio.WindowsSelectorEventLoopPolicy())
    ```

* You may run into issues where pip is using a different python than Jupyter Lab is running. E.g., you may install a package but then Jupyter complains it is unavailable. In that case, instead of `pip install` try running `python -m pip install`. Additionally, check if python is from the same environment as pip using `which pip` or `which pip3` and `which python`.

* You may have trouble using Python and Jupyter Lab with the [Anaconda Distribution](https://www.anaconda.com/distribution/). In that case, one fix is to uninstall Anaconda completely and install basic [Python](https://www.python.org/downloads/).

* The developers of Altair sometimes release a new version via pip and update the documentation before it is stable.
    Note that the documentation version and altair version you are using may be out of sync.
    In this assignment, using the `requirements.txt` file we are asking you to install a particular version to avoid some issues like this.

# Assignment Setup (For Instructors Only)

See https://github.com/NEU-DS-4200-F20-Staff/Assignment_Setup_Instructions.