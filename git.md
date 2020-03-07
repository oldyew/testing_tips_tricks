# GIT

git help <command>

## config

```git
git config --global user.name 'username'
git config --global user.email 'username@dot.com'
git config --list
```

## common

```git
git init
git status
```

## stage(add)

```git
git add <file>
git restore --staged <file>
git add .  # add all files
git add -A # add all file in all dir from any dir
git add -u # add untracked files
git add -p # allow to add changes one by one to already added commits
```

## commits

```git
git commit -m 'text' # make a staged commit
git commit -am 'text' # stage and commit
git commit --amend # add to the last commit
git commit -a --amend --no-edit
```

## remove files

```git
git rm <file> # remove from git and system
git rm --cached <file> # remove from git only
```

## undo changes

```git
git reset # undo all added or removed
git reset <file>
git reset commit_SHA^ # undo commit
git reset --hard commit_SHA^ # undo commnit and restore deleted files
git reset --hard # undo to the previous stage
```

## revert

```git
git revert commit_SHA
git revert -n commit_SHA
```


<!-- git remote add origin 'git url'
git push -u origin master

git pull
git checkout -b [name_of_your_new_branch]
git push remote [name_of_your_new_branch]

git branch -a

git remote add [name_of_your_remote] [name_of_your_new_branch] -->
