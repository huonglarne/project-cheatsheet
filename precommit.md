# Set up

## Install pre-commit with pip or poetry

If use poetry to install, activate the virtual environment before using.

`poetry shell`

Check install

`pre-commit --version`

Remember install pylint in the same environment as pre-commit.

## Config
Add `.pre-commit-config.yaml` file in project folder 

```
repos:
  - repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v4.0.1
    hooks:
      - id: check-yaml
      - id: end-of-file-fixer
      - id: trailing-whitespace

  - repo: https://github.com/asottile/seed-isort-config
    rev: v5.10.1
    hooks:
      - id: seed-isort-config

  - repo: https://github.com/pycqa/isort
    rev: 5.6.4
    hooks:
      - id: isort
        args: ["--profile", "black", "--filter-files"]


  - repo: https://github.com/psf/black
    rev: 22.6.0
    hooks:
      - id: black
        language_version: python3.8

  - repo: https://github.com/pre-commit/mirrors-mypy
    rev: v0.971 # Use the sha / tag you want to point at
    hooks:
      - id: mypy
        args: [--no-strict-optional, --ignore-missing-imports]
        language_version: python3.8

  - repo: https://gitlab.com/pycqa/flake8
    rev: 5.0.3
    hooks:
      - id: flake8
        language_version: python3.8

  - repo: local
    hooks:
      - id: pylint
        name: pylint
        entry: pylint
        language: system
        types: [python]
        args: [
            "--jobs=2",
            "-rn", # Only display messages
            "--rcfile=.pylintrc", # Link to your config file
            "--load-plugins=pylint.extensions.docparams", # Load an extension
          ]

```

## Install hook

`pre-commit install`

# Use

Pre-commit will be ran automatically when committing.

Commit without pre-commit

`git commit -m "Message" --no-verify`