# GIT

git help 'command'

## Config

```git
git config --global user.name 'username'
git config --global user.email 'username@dot.com'
git config --list
```

## Commits

```git
git init
```

### stage(add)

```git
git add <file>
git restore --staged <file>
git add .  # add all files
git add -A # add all file in all dir from any dir
git add -u # add untracked files
git add -p # allow to add changes one by one to already added commits
```

### commits

```git
git commit -m 'text' # make a staged commit
git commit -am 'text' # stage and commit
git commit --amend # add to the last commit
git commit -a --amend --no-edit
```

### remove files

```git
git rm <file> # remove from git and system
git rm --cached <file> # remove from git only
```

### undo changes

```git
git reset # undo all added or removed
git reset <file>
git reset commit_SHA^ # undo commit
git reset --hard commit_SHA^ # undo commnit and restore deleted files
git reset --hard # undo to the previous stage
```

### revert

```git
git revert commit_SHA
git revert -n commit_SHA
```

## History

### Status

```git
git status
```
### Log

```git
git log

git log -n 2
git log -2

git log --oneline
git log --oneline filename

git log --all # all branches

git log --graph

git log --reverse

HEAD -> HEAD~1 -> HEAD~2 -> HEAD~3
HEAD -> HEAD^ -> HEAD^^ -> HEAD^^^
SHA -> SHA~1 or SHA^
```

### Show

```git
git show
git show SHA
git show --name-status
git show HEAD~2:filename
```

### Diff

```git
git diff
git diff --staged
git diff filename
git diff -w # remove whitespaces
git diff HEAD..HEAD~2
get diff HEAD~2..HEAD
```

## Branching

```git
git branch
git branch branch_name
git branch --list
git branch -d branch_name # remove branch
git branch -D branch_name # force remove branch
```

```git
git checkout # switch between branches
git checkout -b branch_name # create and switch to branch
git checkout -- file # discard changes
git checkout -b branch_name SHA # creates new branch from SHA
git checkout SHA # switch to SHA - detahced HEAD
```

```git
git merge
git merge branch_name # when in branch to which it should be merged
```

```git
git rebase master # get stale branch back up to date
git rebase -i SHA^ # cleanup some of commnits

```

```git
git cherry-pick SHA # when in brach where it should be picked
git cherry-pick SHA SHA
git cherry-pick SHA^..SHA # range
git cherry-pick -n SHA # make changes but it's not committed
```

## Sharing Work

```git
git clone URL
git clone URL folder_name
```

```git
git remote
git remote -v
git remote add upstream URL/SSH
git remote rename name name
git remote set-url origin URL
git remote remove
```

```git
git push
git push origin branch_name
git push origin HEAD
git push -u origin HEAD
git push origin :branch_name # remove branch
git push -f origin HEAD
```

```git
git fetch
git fetch --all
git fetch --multiple origin upstream
git fetch --prune origin
```

```git
git pull
git pull origin master
git pull = git fetch + git merge
git pull --rebase origin master
```

```git
```

<!-- git remote add origin 'git url'
git push -u origin master

git pull
git checkout -b [name_of_your_new_branch]
git push remote [name_of_your_new_branch]

git branch -a

git remote add [name_of_your_remote] [name_of_your_new_branch] -->
