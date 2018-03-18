# Cookiecutter for Kaggle projects

_A logical, reasonably standardized, but flexible project structure for doing and sharing data science work._

Mostly using Conda.

## Prerequisites

* [Anaconda](https://www.anaconda.com/download/) >=5.x

## Quickstart

The following instructions assume you are working on a Windows 7 workstation.

### Creating the conda environment with cookiecutter

```
conda env create -f environment.yml
activate cookiecutter-kaggle
```

### Generate project

You should have activated your virtual environment before pursuing.

In a folder where you want your project generated : 
`cookiecutter https://github.com/andfanilo/cookiecutter-kaggle.git`

You can also clone the project in `<path/to/template>`, 
and from the folder where you want to generate your project, launch `cookiecutter <path/to/template>`

Complete the values for your project and voilà !

## Contributing guide

All contributions, bug reports, bug fixes, documentation improvements, enhancements and ideas are welcome.

## Credits

This project is heavily influenced by [this cookiecutter](https://github.com/drivendata/cookiecutter-data-science)