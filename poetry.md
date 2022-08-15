# Install

`pip install poetry`

`poetry init`

# Use

## Install packages using `pyproject.toml` file

`poetry install`

## Activate poetry environment for running in terminal

`poetry shell`

Get path to poetry environment

`poetry show -v`

## Add package

`poetry add pakage-name`

`poetry add pakage-name@specfic_version`

## Remove package

`poetry remove package-name`

## Add many packages at once in order

Create `requirements.txt` file

```
poetry
pre-commit
mypy
black
flake8
isort
pylint
pytest
```

Add all packages in requirements

`poetry add $( cat requirements.txt )`
