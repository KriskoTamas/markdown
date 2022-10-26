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

<img src="data:image/png;base64,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">

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