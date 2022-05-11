# Clone private repo

`git clone https://username@github.com/NAME/repo.git`

# Config user for repo

Remember to config this before committing

`git config user.name "username"`

`git config user.email "email"`

`git config credential.helper store`

# Branch commands

## Create branch

Create new branch

`git checkout -b branch-name`

Push branch to remote

`git push -u origin branch-name`

## Create local branch to track remote branch

List remote branches

`git branch -r`

Create local branch to track remote branch

`git checkout -b local_name origin/remote_name`

## Delete branch

Delete local branch

`git branch -d local-branch-name`

Delete both local and its remote

`git push --delete remote-branch-name local-branch-name`

# Staging and commit

## List changes

`git diff --name-only`

## List staged files

`git diff --name-only --cached`

# Trouble pushing to private repo

`git remote set-url origin git@github.com:username/repo.git`