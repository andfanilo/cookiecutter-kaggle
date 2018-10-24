# Cookiecutter for Kaggle Conda projects

This is a template cookiecutter project for bootstrapping your work on Kaggle competitions. It contains :

- a directory structure for sorting your notebooks, data, models, figures, tasks and source code to reuse in notebooks
- a conda environment file with the basic python libraries and some extras :
  - numpy / pandas / scikit-learn / seaborn / statsmodels / plotly / jupyterlab classic Data Science stack
  - [keras](https://keras.io/) and [lightgbm](https://lightgbm.readthedocs.io/en/latest/) for prediction
  - [pyspark](https://spark.apache.org/) and [h2o](https://www.h2o.ai/) for distributed processing
  - [pandas-profiling](https://github.com/pandas-profiling/pandas-profiling) for generating HTML reports on pandas dataframes
  - [missingno](https://github.com/ResidentMario/missingno) for missing data analysis
  - [invoke](http://docs.pyinvoke.org/) as a replacement to `Makefile` for managing project tasks
  - [nbdime](https://github.com/jupyter/nbdime) for diffing and merging notebooks
  - [kaggle-api](https://github.com/Kaggle/kaggle-api) a CLI for interacting with Kaggle API
  - [path.py](https://pathpy.readthedocs.io/en/stable/) for browsing files in Python

## Prerequisites

- [Anaconda](https://www.anaconda.com/download/) >=5.x
- [Cookiecutter](https://github.com/audreyr/cookiecutter) >= 1.4.0: This can be installed with pip by or conda depending on how you manage your Python packages:

```bash
$ pip install cookiecutter
```

or

```bash
$ conda config --add channels conda-forge
$ conda install cookiecutter
```

## Generate a new project

In a folder where you want your project generated :
`cookiecutter https://github.com/andfanilo/cookiecutter-kaggle.git`

You can also clone the project in `<path/to/template>`,
and from the folder where you want to generate your project, launch `cookiecutter <path/to/template>`

It will ask for the following values :

```
full_name
email
project_name
project_short_description
version
```

Complete the values for your project and voilà ! Then follow the `README` inside your new project for further installation.

## Contributing guide

All contributions, bug reports, bug fixes, documentation improvements, enhancements and ideas are welcome.

## Credits

This project is heavily influenced by [drivendata's Data Science cookiecutter](https://github.com/drivendata/cookiecutter-data-science).

Other links that helped shape this cookiecutter :

- [Write less terrible code with Jupyter Notebook](https://blog.godatadriven.com/write-less-terrible-notebook-code)
- [Cookiecutter DataScience Opinions](http://drivendata.github.io/cookiecutter-data-science/#opinions)
