# Git commands cheat sheet

## Links
Git main page: https://git-scm.com/

Git documentation: https://git-scm.com/docs

Learn Git branching: https://learngitbranching.js.org/

## Check git version
```sh
git --version
```

## Help
Show help page related to a specific command
```sh
git help
git help <command>
```

## Show
Shows the log message and textual diff
```sh
git show <commit>
```

## Log
Show recent commits on repository

Type `:q` for exit
```sh
git log
```

```sh
git log -n <number>
```

```sh
git log --author=<author>
```

### Filter by date

Date can be:
- relative like "yesterday" or "today"
- relative, like "9:00" or "9AM", which means today at 9:00
```sh
git log --after=<date>
```

```sh
git log --before=<date>
```

## Status
Show the state of the repository and the staging area. List the changed files and those you need to stage and commit.
```sh
git status
```

## Config
Show git config
```sh
git config --list
```
Get value for a given key
```sh
git config --get <key>
```

Set value for a key in global scope
```sh
git config --global <key> <value>
```

Common keys are: `user.name`, `user.email`

## Initialize repository
Create an empty Git repository or reinitialize an existing one
```sh
git init
```

## Clone
Clone a repository into a new directory
```sh
git clone <url>
```

Clone into CURRENT folder (dot at the end)
```sh
git clone <url> .
```

## Staging
Add specific files to the staging area
```sh
git add <filename>
git add <filename> <filename>
```

Add all files to the staging area

**Note:** `git stage` is a synonym for `git add`, there is no difference in usage.
```sh
git add *
git add .
git stage *
git stage .
```

Remove specific files from staging
```sh
git restore --staged <filename>
git restore --staged <filename> <filename>
```

Remove all files from staging
```sh
git restore --staged *
git restore --staged .
```

## Commit
Commit specific file
```sh
git commit <filename> -m <message>
```

Commit staged changes to local repository
```sh
git commit -m <message>
```

Commit with additional description (optional)
```sh
git commit -m <message> -m <optionalMessage>
```

Commit both staged and unstaged files but not new files (only modified and deleted)
```sh
git commit -a -m <message>
git commit -am <message>
```

There are cases, when you mess up your commit (typo in commit message or missed out files), in these cases you can use the `--amend` flag
```sh
git commit --amend
```

## Reset
**Reset modes:**

`--soft`: Soft reset, moves changes to the staging area

`--mixed`: Mixed reset, moves changes to the working directory

`--hard`: Hard reset, changes to the files will be removed permanently

**Note:** If `<mode>` is omitted, it defaults to `--mixed`.
```sh
git reset [--soft | --mixed | --hard] <commit>
```

**Undo Reset:**
```sh
git reset --hard HEAD@{1}
```

**`<commit>` can be:**

`Commit hash or the beginning of the hash (at least the first 4 characters)`: Resets the HEAD to that specific commit

`HEAD^`: Resets last commit

`HEAD^^`: Resets last 2 commits

`HEAD~1`: Resets last commit

`HEAD~10`: Resets last 10 commits


### Links
[Git tree movements](https://i.stack.imgur.com/qRAte.jpg)

## Revert
Creates a new commit that undoes the changes from a previous commit

Default revert commit message:
Revert "`<commitMessage>`"
```sh
git revert <commit>
```

## Remote
Add the remote repository
```sh
git remote add <repositoryName> <server>
```

Remove the remote repository
```sh
git remote remove <repositoryName>
git remote rm <repositoryName>
```

Rename the remote repository
```sh
git remote rename <oldRepositoryName> <newRepositoryName>
```

List all currently configured remote repositories
```sh
git remote [-v | --verbose]
```

## Pull
Fetches the changes from the remote repository and also updates the remote-tracking branches

**Note:** `git pull` basically runs `git fetch` with the given parameters and then depending on configuration options or command line flags, will call either `git rebase` or `git merge` to reconcile diverging branches
```sh
git pull
git pull <repositoryName> <branch>
```

## Fetch
Fetches the changes from the remote repository, but doesn't apply them

This operation is **safe to run at any time** since it never changes any of your local branches
```sh
git fetch
```

## Push
Push the branch to a remote repository
```sh
git push [...options] <repositoryName> <branch>
# Options
[-f | --force] # Force push
```

Failed to push because branch is behind its remote couterpart

```diff
$ git push
! [rejected]    master -> master (non-fast-forward)
- error: failed to push some refs to 'https://github.com/KriskoTamas/git-test.git'
! hint: Updates were rejected because the tip of your current branch is behind
! hint: its remote counterpart. Integrate the remote changes (e.g.
! hint: 'git pull ...') before pushing again.
! hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```

## Branching
List all the branches in your repository
```sh
git branch
```

Create a new branch
```sh
git branch <branch>
```

Rename a branch
```sh
git branch <newBranchName> # Rename current branch
git branch <oldBranchName> <newBranchName> # Rename another branch
```

Create a new branch and switch to that branch
```sh
git checkout -b <branch>
```

Delete a branch
```sh
git branch [-d | --delete] <branch>
```

Switch to another branch
```sh
git checkout <branch>
```

## Merge
Merge another branch with current branch (target branch)
```sh
git merge <branch>
```

## Rebase
Bring commits from another branch that are ahead of the current branch
```sh
git rebase <branch>
```

## Cherrypick
Bring a specific commit (or commits) from another branch to the current branch (target branch)
```sh
git cherry-pick <commit>
git cherry-pick <commit> <commit>
```

## Checkout

Discard changes to a file (or files) permanently, if it's not in the staging area
```sh
git checkout .
git checkout *
git checkout <file>
git checkout <file> <file>
```

## Stash
**Records the current state of the working directory and the index.**
The command saves your local modifications away and reverts the working directory to match the HEAD commit.

Show files in stash
```sh
git stash show
```

Discard changes to all files in the working directory
```sh
git stash
```

Apply changes in stash
```sh
git stash apply
```

Remove all stash entries
```sh
git stash clear
```

## Reflog
Reference logs, or "reflogs", record when the tips of branches and other references were updated in the local repository
```sh
git reflog
```

```sh
git reflog -n <number>
```

## Diff
Show changes between commits, commit and working tree
```sh
git diff
```

## Fork
A fork creates a completely **independent copy** of Git repository.

## Pull request
A pull request (PR) is an event in Git where a contributor asks a maintainer of a Git repository to review code they want to **merge into** a project.

## .gitignore
The `.gitignore` file tells git which files it should ignore.

There are several files and directories which you often don't want to commit, like automatically generated build files and logs.

Gitignore generator: https://www.toptal.com/developers/gitignore/

# Git GUI clients
GitHub Desktop: https://desktop.github.com/
GitKraken: https://www.gitkraken.com/
SourceTree: https://www.sourcetreeapp.com/

## Misc

Repository name is usually `origin`

Branch name is usually `main` (previously `master`)