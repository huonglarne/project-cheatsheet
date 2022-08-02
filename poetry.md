# Install

`pip install poetry`

`poetry init`

# Activate poetry environment for running in terminal

`poetry shell`

# Add or remove package

`poetry add pakage-name`

`poetry remove package-name`

# Add many packages at once in order

Create `requirements.txt`

```
# basic
python
poetry

# formatting
pre-commit
mypy
black
flake8
isort
pylint

# testing
pytest
```

Add all packages in requirements

`poetry add $( cat requirements.txt )`