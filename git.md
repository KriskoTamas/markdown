# Git commands cheat sheet

## Links:
Git main page: https://git-scm.com/

Git documentation: https://git-scm.com/docs

Learn Git branching: https://learngitbranching.js.org/

## Check git version
```
git --version
```


## Show help page related to the command
```
git help
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
git log --after=<date>
```

```
git log --before=<date>
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
git config --global user.name <user name>
```

Set `user.email` in global scope
```
git config --global user.email <user email>
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
Add specific files to the staging area
```
git add <filename>
git add <filename> <filename>
```

Add all files to the staging area

**Note:** `git stage` is a synonym for `git add`, there is no difference in usage.
```
git add *
git add .
git stage *
git stage .
```

Remove specific files from staging
```
git restore --staged <filename>
git restore --staged <filename> <filename>
```

Remove all files from staging
```
git restore --staged *
git restore --staged .
```

## Commiting
Commit specific file
```
git commit <filename> -m <commit message>
```

Commit staged changes to local repository
```
git commit -m <commit message>
```

Commit both staged and unstaged files but not new files (only modified and deleted)
```
git commit -a -m <commit message>
```

## Reset commits
**Reset modes:**

`--soft`: Soft reset, moves changes to the staging area

`--mixed`: Mixed reset, moves changes to the working directory

`--hard`: Hard reset, changes to the files will be removed permanently

**Note:** If `<mode>` is omitted, it defaults to `--mixed`.
```sh
git reset [--soft | --mixed | --hard] <commit>
```

**`<commit>` can be:**

`Commit hash or the beginning of the hash (at least the first 4 characters)`: Resets the HEAD to that specific commit

`HEAD^`: Resets last commit

`HEAD^^`: Resets last 2 commits

`HEAD~1`: Resets last commit

`HEAD~10`: Resets last 10 commits


### Links:
[Git tree movements](https://i.stack.imgur.com/qRAte.jpg)

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
```sh
git push [...options] <repo name> <branch name>
# Options
[-f | --force] # Force push
```

Failed to push because branch is behind its remote couterpart

![Failed to push](data:image/png;base64,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)

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

Repository name is usually `origin`

Branch name is usually `main` (previously `master`)