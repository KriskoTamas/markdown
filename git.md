# Git commands cheat sheet

## Links:
Git main page: https://git-scm.com/

Git documentation: https://git-scm.com/docs

## Check git version
```
git --version
```


## Show help page related to the command
```
git help <command>
```

## Show recent commits on repository
Type `:q` for exit
```
git log
```

```
git log -n <number of commits to display>
```

```
git log --author="<author>"
```

### Filter by date

Date can be relative like "yesterday" or "today"
```
git log --after="<date>"
```

```
git log --before="<date>"
```

## Status
Show the state of the repository and the staging area. List the changed files and those you need to stage and commit.
```
git status
```

## Show git config
```
git config --list
```

## Config
Set `user.name` in global scope
```
git config --global user.name "<user name>"
```

Set `user.email` in global scope
```
git config --global user.email "<user email>"
```

## Initialize repository
Create an empty Git repository or reinitialize an existing one
```
git init
```

## Clone
Clone a repository into a new directory
```
git clone <path or server>
```

Clone into CURRENT folder (dot at the end)
```
git clone <path or server> .
```

## Staging
Add specific file(s) to staging
```
git add <filename> <filename>
```

Add all files to staging
```
git add *
git add .
```

Remove specific file(s) from staging
```
git restore –staged <filename>
```

Remove all files from staging
```
git restore --staged *
git restore --staged .
```

## Commiting
Commit staged changes to local repository
```
git commit -m "<commit message>"
```

Commit both staged and unstaged files but not new files (only modified and deleted)
```
git commit -a -m "<commit message>"
```

## Revert commits
```
git reset --soft HEAD~1 # Revert last commit
git reset --soft HEAD~2 # Revert last 2 commits
```

## Resets the current branch head to <commit> and permanently removes the modifications to the files
```
git reset --hard <commit>
```

## Remote
Add the remote repository
```
git remote add <repo name> <server>
```

Remove the remote repository
```
git remote remove <repo name>
git remote rm <repo name>
```

Rename the remote repository
```
git remote rename <old> <new>
```

List all currently configured remote repositories
```
git remote -v
```

## Fetch from and integrate with another repository or a local branch
```
git pull
```

## Fetch from a branch in another repository
```
git pull <repo name> <branch name>
```

## Push the branch to your remote repository
```
git push <repo name> <branch name>
```

## Branching
List all the branches in your repository
```
git branch
```

Create a new branch
```
git branch <branch name>
```

Delete a branch
```
git branch --delete <branch name>
git branch -d <branch name>
```

Switch to other branch
```
git checkout <branch name>
```

## Merging
Merge another branch with current branch
```
git merge <branch name>
```

## Show diff
```
git diff
```

Repository name is usually **'origin'**

Branch name is usually **'main'** (previously **'master'**)

