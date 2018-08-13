# {{ cookiecutter.project_name }}

{{ cookiecutter.project_short_description }}

## Prerequisites

- [Anaconda](https://www.anaconda.com/download/) >=5.x

## API credentials

To use the Kaggle API, sign up for a Kaggle account at https://www.kaggle.com. Then go to the 'Account' tab of your user profile (`https://www.kaggle.com/<username>/account`) and select 'Create API Token'. This will trigger the download of `kaggle.json`, a file containing your API credentials. Place this file in the location `~/.kaggle/kaggle.json` (on Windows in the location `C:\Users\<Windows-username>\.kaggle\kaggle.json`).

For your security, ensure that other users of your computer do not have read access to your credentials. On Unix-based systems you can do this with the following command:

`chmod 600 ~/.kaggle/kaggle.json`

# Installation guide

## Set up conda environment

Using conda:

```
conda env create -f environment.yml
activate {{ cookiecutter.project_slug }}
```

The packages necessary to run the project are now installed inside the conda environment.

**Note: The following sections assume you are located in your conda environment.**

## Set up project's module

To move beyond notebook prototyping, all reusable code should go into the `src/` folder package. To use that package inside your project, install the project's module in editable mode, so you can edit files in the `src/` folder and use the modules inside your notebooks :

```
pip install --editable .
```

To use the module inside your notebooks, add `%autoreload` at the top of your notebook :

```
%load_ext autoreload
%autoreload 2
```

Example of module usage :

```py
from src.data.make_dataset import generate
generate(10)
```

# Invoke command

We use [Invoke](http://www.pyinvoke.org/) to manage an
unique entry point into all of the project tasks.

List of all tasks for project :

```
$ invoke -l

Available tasks:

  lab     Launch Jupyter lab
```

Help on a particular task :

```
$ invoke --help lab
Usage: inv[oke] [--core-opts] notebook [--options] [other tasks here ...]

Docstring:
  Launch Jupyter lab

Options:
  -i STRING, --ip=STRING   IP to listen on, defaults to *
  -p, --port               Port to listen on, defaults to 8888
```

You will find the definition of each task inside the `tasks.py` file, so you can add your own.

_PS : we don't use Makefile because some people work on Windows workstations and the
install of make is cumbersome on those._

# Project organization

    ├── tasks.py           <- Invoke with commands like `notebook`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── environment.yml    <- The requirements file for reproducing the analysis environment
    │
    └── src                <- Source code for use in this project.
        ├── __init__.py    <- Makes src a Python module
        │
        ├── data           <- Scripts to download or generate data
        │   └── make_dataset.py
        │
        ├── features       <- Scripts to turn raw data into features for modeling
        │   └── build_features.py
        │
        ├── models         <- Scripts to train models and then use trained models to make
        │   │                 predictions
        │   ├── predict_model.py
        │   └── train_model.py
        │
        └── visualization  <- Scripts to create exploratory and results oriented visualizations
            └── visualize.py
