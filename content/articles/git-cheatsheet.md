---
title: Git cheatsheet
summary: "A work in progress git cheatsheet for basic commands and common actions "
published: false
createdAt: 2022-02-14T14:01:24.223Z
---
## Show working directory status
```
git status
```

## Show commit history
```
git log
```

## Branches

### Show local branches
```
git branch
```

### Create a new branch
```
git checkout -b [branchname]
``` 

## Create an alias for a prettier log file in your `.bashrc` or `.bash-profile`
```
alias gitlog="git log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --branches"
```

## Move commits to a seperate branch
This one only works I have not pushed the commits that I want to move to the remote. As an example I am on master branch and I have committed 2 commits that I   want to move to a separate branch. What I can do is create a new branch and move back to master branch.

```
git checkout -b feature/my-new-feature
git checkout master
```
Now I need to run a `git log` or `gitlog` to find the commit identifier and reset the master branch back 2 commits. The 2 commits are then already on the new branch created and have been removed from master branch.

```
gitlog
git reset --hard [commit identifier] 
```

## Mergin and rebasing
I have two options when I want changes from one branch to be merged into another using merge I will create a new new commit with all the changes that are ahead to my branch. So if there are 10 new commits on master branch this will create a new commit on my branch with all the changes from the 10 commits. So when I am on a feature branch and I want to get the latest from master I run:

```
git merge master
```

On the other hand if I do not want to create that extra merge commit but instead get all 10 commits from master I run `git rebase` and then my feature branch commits will stay on top of the commits from master just like as if I just created that feature branch I am on. So in this example where I am on a feature branch where I want latest commits from master I run:
  
```
git rebase master
```

Note: I only use `git rebase` when I am the only one working on that feature branch.
