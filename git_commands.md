# Clone

Clone private repo

`git clone https://username@github.com/NAME/repo.git`

# Config user for repo

## See config for current repo

`git config --list`

## Set user

`git config user.name "username"`

`git config user.email "email"`

## Store password after entering

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

# Stage, commit and push

## List

List changes

`git diff --name-only`

List staged files

`git diff --name-only --cached`

List unpushed commits

`git log --branches --not --remotes`

## Undo

Undo commit

`git reset --soft HEAD`

## Pushing

Create new remote branch from push

`git push -u origin remote_branch_name`

Trouble pushing to orivate repo

`git remote set-url origin https://username@github.com/NAME/repo.git`