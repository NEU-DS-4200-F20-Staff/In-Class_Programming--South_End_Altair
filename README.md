# In-Class Programming — South End Altair

~*25 min total*

This repository is your starting point for the tutorial and includes instructions below.

# Aim of the tutorial

[Altair](https://altair-viz.github.io/) is a declarative statistical visualization library for Python, based on [Vega](http://vega.github.io/vega) and [Vega-Lite](http://vega.github.io/vega-lite).
In this tutorial you will learn how to use Jupyter Lab and Altair.
If you run into problems see the **Tips, tricks, and troubleshooting** section below.

# Instructions

## Setup instructions

1. Clone the repo.
1. `CD` to the repo directory. Create and activate a virtual environment for this project. You may need to modify the code you use depending on what Python you have installed and how your machine is configured.

1. Run the setup commands below.

    * On macOS or Linux, run these three commands *separately* in case there are errors:
        ```
        python3 -m venv env
        ```
        ```
        source env/bin/activate
        ```
        ```
        which python
        ```
    * On Windows, run these three commands *separately* in case there are errors:
        ```
        python -m venv env
        ```
        ```
        .\env\Scripts\activate.bat
        ```
        ```
        where.exe python
        ```
    Check the path(s) provided by `which python` or `where.exe python` — the first one listed *should* be inside the `env` folder you just created.

1. Install necessary packages. Note that you should install the exact versions of the packages.
    ```
    pip install -r requirements.txt
    ```
    This may take a few minutes.

If you have trouble running any of these steps, see the [Troubleshooting section](#troubleshooting) below.

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

1. Only if you have made any changes to the required packages you should export a list of all installed packages and their versions:
   ```
   pip freeze > requirements.txt
   ```

1. **Before you commit a Jupyter Notebook .ipynb file, clear the outputs of all cells.** This decreases file size, removes unnecessary metadata, and makes diffs easier to understand. In Jupyter Lab you can use the GUI: Edit->Clear All Outputs.

1. Make sure to add all your required files, including the .ipynb file and any images.

1. Finally, commit all your local code and push it to your remote GitHub Classroom-generated repository.

# Submission instructions

* Submit the link to your GitHub repository on Canvas.

# Tips, tricks, and troubleshooting

See https://github.com/NEU-DS-4200-F20-Staff/General_Course_Information/blob/master/altair.md

# Assignment setup (for instructors only)

See https://github.com/NEU-DS-4200-F20-Staff/General_Course_Information/blob/master/assignment-setup.md