# Set up

## Install pre-commit

Install using pip or poetry.

Activate the virtual environment before using. If use poetry to install:

`poetry shell`

Check install

`pre-commit --version`

## Instal pyline

Install pylint in the same environment as pre-commit.

Create a `.pylintrc` file in the root of project folder. See the example file in the `ci` folder.

## Config

Add `.pre-commit-config.yaml` file in project folder. See the example file in the `ci` folder.

## Install hook

`pre-commit install`

# Use

## Initialize

Remember to activate the environment where pre-commit and pylint are installed before using.

Run pre-commit over all current files in the first time to init new repo.

`pre-commit run --all-files`

## Basic use

Pre-commit will be ran automatically when committing.

Commit without pre-commit

`git commit -m "Message" --no-verify`

## Disable by adding comment to code

Disable line or block of code

`# pylint: disable=no-member`

Disable broad except

`# pylint: disable=broad-except`
