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

```diff
+ Green
- Red
! Orange
@@ Pink @@
# Gray
```

```
$ git push
! [rejected]    master -> master (non-fast-forward)
error: failed to push some refs to 'https://github.com/KriskoTamas/git-test.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
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

Repository name is usually `origin`

Branch name is usually `main` (previously `master`)