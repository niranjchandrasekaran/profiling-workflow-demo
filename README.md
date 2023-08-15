This repository was created from the `cytomining/profiling-template` template repository. The `README.md` of that repository and that of `cytomining/profiling-recipe` contain instructions on how to
- create a data repository
- weld `profiling-recipe` to the data repository
- create the folder structure and populating them with the necessary files
- edit the `config.yml` file
- run the profiling recipe

To reproduce the profiles in this repo, clone the repo (with git's [git-lts extension](https://git-lfs.com/))

```bash
git clone git@github.com:niranjchandrasekaran/profiling-workflow-demo.git
```

# Installation

## External dependencies
To plot the results first install [orca](https://github.com/plotly/orca).

## Python dependencies
You can then use conda (traditional way) or poetry (new way) to install the dependencies:

### Conda
Install miniconda (we use Anaconda as our package manager. Install Miniconda following the instructions [here](https://docs.conda.io/en/latest/miniconda.html)) and `git-lfs`

Install the conda environment

```
cd profiling-workflow-demo
conda env create --force --file environment.yml
conda activate profiling
```

and then run the following command

```bash
python profiling-recipe/profiles/profiling_pipeline.py --config config_files/config.yml
```

### Poetry

Set up [poetry](https://python-poetry.org/docs/#installation). It will automatically create a new virtual environment for this project with python 3.8.

```
cd profiling-workflow-demo
poetry install
```

Then, to produce the figures and statistics again you can do
```
cd analysis
poetry run jupyter notebook 0.calculate-ap.py
```
