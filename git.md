# GIT

```git

git help <command>


## config

```git

git config --global user.name 'username'
git config --global user.email 'username@dot.com'
git config --list

## common

```git

git init
git status

## add(stage)/unstage

```git
git add <file>
git restore --staged <file>
git add .  # add all files
git add -A # add all file in all dir from any dir
git add -u # add untracked files
git add -p # allow to add changes one by one to already added commits

## commits

```git

git commit -m 'text' # make a staged commit
git commit -a -m 'text' # add/stage and commit 
git commit --amend
git commit -a --amend --no-edit

## remove files

```git
git rm <file> # remove from git and system
git rm --cached <file> # remove from git only
