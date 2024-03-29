# Clone

Clone private repo

`git clone [https://username:personal_access_token@github.com/NAME/repo.git
](https://username:personal_access_token@github.com/NAME/repo.git)`

Clone repo as submodule

`git submodule add repo_url`

# Config user for repo

## See config for current repo

`git config --list`

## Reset global user

 `git config --global user.name ""`
 
`git config --global user.email ""`

## Set user for a repo

`git config user.name "username"`

`git config user.email "email"`

## Store password after entering

`git config credential.helper store`

# Branch commands

## Create branch

Create new branch

`git checkout -b branch-name`

Push current local branch to remote

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

## Commit

Undo commit

`git reset --soft HEAD`

Undo commit and unstage files

`git reset HEAD`

Change message of last commit

`git commit --amend -m "new message"`

## Pushing

Trouble pushing to private repo

`git remote set-url origin https://username:personal_access_token@github.com/NAME/repo.git`

Trouble pushing even after user config

`git push https://username:personal_access_token@github.com/username/repository.git`

# Submodule

Add submodule

    git submodule add https://github.com/NAME/repo.git
    git submodule init

Make parent repo update latest change on submodule

    git pull --recurse-submodules
    git submodule update --remote
    git add .
    git commit -m 'update submodules'
    git push
